#Task 06

Напиши израз во релациона алгебра што ќе ги прикаже имињата и презимињата на судиите кои оценувале професионални скијачи што имаат светски ранг подобар од 10, но не оцениле ниту еден рекреативен скијач.

P = π Evaluates.judge_id (
    (σ Professional.world_ranking < 10 (Professional)
     join Professional.skier_id = Participation.skier_id Participation)
    join Participation.id = Evaluates.participation_id Evaluates
)

R = π Evaluates.judge_id (
    (Recreational join Recreational.skier_id = Participation.skier_id Participation)
    join Participation.id = Evaluates.participation_id Evaluates
)

K = P - R

π Judge.first_name, Judge.last_name (
    K join Evaluates.judge_id = Judge.id Judge
)
