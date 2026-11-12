#Task 08

Напиши израз во релациона алгебра што ќе ги прикаже шифрите на рекреативните скијачи кои имаат претплата на планот Basic или Standard, но немаат претплата на планот Premium.


A = σ Membership_plan.name = 'Basic' or Membership_plan.name = 'Standard' (Membership_plan)

B = σ Membership_plan.name = 'Premium' (Membership_plan)

C = π Recreational.skier_id (
    (A join Membership_plan.id = Subscription.membership_plan_id Subscription)
    join Subscription.recreational_id = Recreational.skier_id Recreational
)

D = π Recreational.skier_id (
    (B join Membership_plan.id = Subscription.membership_plan_id Subscription)
    join Subscription.recreational_id = Recreational.skier_id Recreational
)

C - D
