#Task 04

Напиши израз во релациона алгебра што ќе ги прикаже имињето и презимето на лизгачите со националност ‘Macedonian’, заедно со имињата на лизгалиштата на кои учествувале на натпревар.


A = σ nationality = 'Macedonian' (Skier) --prvo gi birame site makedonci 

B = A join Skier.id = Participation.skier_id Participation -- so ova doznavame na koj natprevari uchestvuvale tie lizgachi 

C = B join Participation.competition_id = Held_Competition.competition_id and Participation.held_date = Held_Competition.date Held_Competition -- proveruvame dali se sovpagja shifrata na natprevarot i datumot 

D = C join Held_Competition.ice_rink_id = Ice_Rink.id Ice_Rink -- go naogjame lizgalishteto t.e imeto 

π Skier.first_name, Skier.last_name, Ice_Rink.name (D) -- gi pechatime samo
