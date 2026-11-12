#Task 05

Напиши израз во релациона алгебра што ќе ги прикаже имињето и презимето на судиите што оцениле барем еден професионален лизгач, но никогаш не оцениле рекреативен лизгач.

--tuka gi naogjame sudiite shto ocenile profesionalci, koj uchestvuval i dali e profesionalec/
A = π judge_id (
    (Evaluates join Evaluates.participation_id = Participation.id Participation)
    join Participation.skier_id = Professional.skier_id Professional
)

--tuka istoto samo za rekreativci 
B = π judge_id (
    (Evaluates join Evaluates.participation_id = Participation.id Participation)
    join Participation.skier_id = Recreational.skier_id Recreational
)

--od site tie pravime razlika
C = A - B

--razlikata ja pechatime
π first_name, last_name (
    Judge join Judge.id = Evaluates.judge_id C
)
