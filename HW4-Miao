str(new_cali_wages)
mean_wage <- new_cali_wages %>% group_by(entity_county, position) %>% 
  summarise(mean_wages = mean(total_wages))

max_wage <- mean_wage %>% group_by(entity_county) %>%
  summarise(max_wage = max(mean_wages))

max_wage_idx <- mean_wage %>% group_by(entity_county) %>%
  summarise(max_idx = which.max(mean_wages), n = n())

View(mean_wage)
View(max_wage)

for(i in 1:nrow(max_wage)){
  max_wage$position[i] <- mean_wage$position[sum(max_wage_idx$n[0:(i-1)]) + max_wage_idx$max_idx[i]]
}
View(max_wage)
