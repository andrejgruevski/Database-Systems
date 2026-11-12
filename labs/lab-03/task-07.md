#Task 07

Напиши израз во релациона алгебра што ќе ги прикаже имињата и презимињата на рекреативните скијачи кои учествувале на натпревар што се одржал на лизгалиштe со статус OPEN

A = Skier join Skier.id = Recreational.skier_id Recreational

B = A join Recreational.skier_id = Participation.skier_id Participation

C = B join Participation.competition_id = Held_Competition.competition_id and Participation.held_date = Held_Competition.date Held_Competition

D = σ Ice_Rink.status = 'OPEN' (Ice_Rink)

π Skier.first_name, Skier.last_name (
    C join Held_Competition.ice_rink_id = Ice_Rink.id D
)
