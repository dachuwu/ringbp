## demo 20200506
library(ringbp)
library(ggplot2)

extract_Rj <- function(obk){
  df <- obk$case_data[infector>0]
  as.vector(table(df$infector))
  }


res <- ringbp::scenario_sim(n.sim = 1,
                            num.initial.cases = 5,
                            prop.asym=3/19, prop.ascertain = 0.9,
                            cap_cases = 1E5, cap_max_days = 1E5,
                            r0isolated = 0, r0community = 2.5, disp.com = 0.16, disp.iso = 1,
                            incu_shape = 3.39,incu_scale = 2.28,
                            delay_shape = 1.02,delay_scale = 5.97,
                            k = 0.7, quarantine = T)
dfcase <- res$case_data[[1]]




# Plot of weekly cases
ggplot2::ggplot(data=res, ggplot2::aes(x=week, y=cumulative, col = as.factor(sim))) +
  ggplot2::geom_line(show.legend = FALSE, alpha=0.3) +
  ggplot2::scale_y_continuous(name="Number of cases") +
  ggplot2::theme_bw()

ringbp::extinct_prob(res,cap_cases = 4500)


####
obk <- outbreak_model(num.initial.cases = 5,
                       prop.ascertain = .3,
                       cap_max_days = 365,cap_cases = 1000,
                       r0isolated = 0,r0community = 2.5,
                       disp.iso = 1,disp.com = 0.16,
                       incu_shape = 3.39,incu_scale = 2.28,
                       delay_shape = 1.02,delay_scale = 5.97,
                       k = 0.7,
                       prop.asym = 3/19,
                       quarantine = T)

dfcase <- res$case_data












