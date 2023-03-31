# Model-populacji
Raport i program zostały stworzone przez Adelę Żelachowską i Martę Korpacz

# Jak korzystać? - Przykładowe uruchamianie
1. Zdefiniuj parametry (więcej w raporcie)

N = 1000 #ile osobników

l = 2 # ile cech ma genom

p = 0.075 # szansa na mutację

var = 0.01 #wariancja rozkładu określająca siłę mutacji

optimal_genotype = [0 for _ in range(0,l)]

selection_variable = 0.50 # współczynnik selekcji

rate = 0.001 # siła zmian środowiska

catastrophic_scenario = False # czy model ma uwzględniać scenariusz katastroficzny? 

n_of_generations = 100  

2. Stwórz populacje i urochom symulację
pop_1 = Population(N, l, p, var, optimal_genotype, selection_variable, rate, catastrophic_scenario)

records = pop_1.simulation(n_of_generations)

3. Obserwuj zmiany!

records.plot_gen_changes() - zwraca wykres obrazujący zmiany średnich genotypów w czasie

records.n_of_inds - zwróci listę z rozmiarem populacji w kolejnych krokach

Możesz także generować wykresy pokazujące średnie przebiegi wielu populacji:

plotting_avarage_N(list_of_histories)

# Katastrofa
1. Ustaw catastrophic_scenario = True
2. Stwórz populację i uruchom symulację
3. Otrzymasz dwa recordy - pierwszy pokazujący losy populacji po katastrofie i drugi pokazujący, co by się działo, gdyby do niej nie doszło
