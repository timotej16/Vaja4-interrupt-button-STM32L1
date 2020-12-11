# Vaja4-interrupt-button-STM32L1

Postopek inicializacije periferije:
b) V Pinout % Configuraton pogledu glede na vašo razvojno ploščico ugotovite, ali lahko uporabite modro tipko za digitalni vhod kot interrupt (GPIO_EXT…). 
Če da, kateri pin je to? ______PA0 (GPIO EXIT0)______
c) Zapišite naslov izhodnih pinov za zeleno in modro LED: 
___________ZELENA LED: LD3 (PC9) in MODRA LED: LD4 (PC8)_____________

Programiranje v IDE:
c) Znotraj te funkcije zapišite ukaz za vklop/izklop zelene LED (pomagajte si z metodo toggle, glej vaja0a). _____HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9)_____.
d) Znotraj iste funkcije dodajte še zakasnitev, ki je potrebna, ko uporabimo mehanska tipkala/stikala:
for(uint32_t i=0; i<10000; i++);
Koliko znaša (v mili sekundah) zapisana zakasnitev, ki jo proizvede zanka for? ___2,8125 ms ___.
e) V user code begin 3 - zanka while(1) - zapišite ukaz za utripanje modre LED (metoda toggle, glej vaja0a): _____HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_8)_____.
f) V to zanko dodajte ukaz za zakasnitev z funkcijo Delay iz knjižnice HAL, in sicer pol sekunde (glej vaja0a): ___HAL_Delay(500)___.

Naložitev kode (Run) in opazovanje delovanja na STM32L1:
a) Opazujte delovanje (utripanje modre LED). Kaj se zgodi, ko pritisnemo na modro tipko na STM32L1?
____Ob pritisku modre tipko se prižiga in ugaša zelena LED dioda. Modra led dioda pa vedno utripa s frekvenco 1 Hz.____
b) Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj? _____Pritisk na modro tipko ne vpliva na utripanje modre LED, ker smo nastavili interrupt na tipko_____.
