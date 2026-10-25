# Глубокое исследование POS

**Статус:** 🟡 v1 (25.10.2026) — матрица, логистика и экономика заполнены по открытым источникам 2024–2026; прикладной кейс — [05_School_100_Days_Scenario.md](05_School_100_Days_Scenario.md)

## Назначение

Сквозное исследование концепции «закрытия позиционного района»: состав средств, логистика развёртывания, экономика. Связанные модули L3: `Logistics_POS`, `Economic_Model`, а также все модули обнаружения и C2. Уровень документа — отраслевая и архитектурная аналитика, без тактических инструкций.

Базовые L1: [L1-20261018-001 исходная концепция](L1_Raw_Data/documents/2026-10-18_Concept_Original_Lev.md); дайджесты 25.10.2026 [T1](L1_Raw_Data/daily_digest/2026-10-25_T1_Aerostats.md) · [T2](L1_Raw_Data/daily_digest/2026-10-25_T2_Persistent_Drones.md) · [T3](L1_Raw_Data/daily_digest/2026-10-25_T3_Layered_CUAS.md) · [T4](L1_Raw_Data/daily_digest/2026-10-25_T4_Saturation_Waves.md) · [T5](L1_Raw_Data/daily_digest/2026-10-25_T5_Civil_Protection.md) · [T6](L1_Raw_Data/daily_digest/2026-10-25_T6_Simulation_Training.md).

## Матрица (угрозы × средства × эшелоны)

Эшелоны — по Эксперту ([L1-20261018-001](L1_Raw_Data/documents/2026-10-18_Concept_Original_Lev.md)): **дальняя** зона (внешние/государственные данные, «формуляр цели»), **средняя** (~2,5 км, собственные быстрые данные), **ближняя** («сектор, за который отвечаешь головой»), плюс **объектовый** эшелон пассивной защиты (добавлен по T5).

| Класс средства | Дальняя | Средняя | Ближняя | Объект | Ограничения | Ориентир цены | Источник |
|---|---|---|---|---|---|---|---|
| Данные государства / соседних районов | ● основной | ○ | — | оповещение | доступ, задержка, правовой статус | — | Эксперт; EDDI ЕС ([EC](https://ec.europa.eu/commission/presscorner/api/files/document/print/en/ip_26_364/IP_26_364_EN.pdf)) |
| Аэростат с РЛС/ОЭС | ● | ● | ○ | — | ветер, заметность, гелий, экипаж | $5,3 млн/год эксплуатации (США) | [T1](L1_Raw_Data/daily_digest/2026-10-25_T1_Aerostats.md) |
| Акустическая сетка | ● (сетью) | ● | ○ | — | шум, ветер, точность | $300–1000/датчик | [Army](https://api.army.mil/e2/c/downloads/2026/04/30/af450e75/no-26-1115-listening-to-the-sky-acoustic-drone-detection-in-ukraine-mar-26.pdf), [MDAA](https://missiledefenseadvocacy.org/wp-content/uploads/2024/07/Team-6-Acoustic-Lily-Pads-Final-Report.pdf) |
| Пассивный RF | ● | ● | ○ | — | «радиомолчащие» цели | контракт $100 млн (Hidden Level) | [Hidden Level](https://www.hiddenlevel.com/press/department-of-war-awards-hidden-level-100-million-ota-to-scale-passive-sensing-technology) |
| Компактная РЛС (MESA и т.п.) | ○ | ● | ● | — | горизонт, излучение | IDIQ до $250 млн (Echodyne) | [Echodyne](https://www.echodyne.com/newsroom/echodyne-awarded-250-million-jiatf-401-counter-uas-contract) |
| Привязной дрон / drone-in-a-box (ОЭС, ретранслятор) | — | ● | ● | ● (осмотр) | время полёта, погода | €3 млн контракт (Elistair) | [T2](L1_Raw_Data/daily_digest/2026-10-25_T2_Persistent_Drones.md) |
| Дроны-перехватчики | — | ● | ● | — | операторы, погода, ночь | $1–5 тыс./шт | [Politico](https://www.politico.eu/article/war-in-ukraine-interceptor-drones-russia-shahed-drones/) |
| Пушки с дистанционным подрывом | — | ○ | ● | — | цена комплекса, высота цели | Skynex ~€60–73 млн; ~10 снарядов/цель | [Defense Express](https://en.defence-ua.com/video/how_many_airburst_bullets_it_takes_to_down_a_shahed_136_video-90.html) |
| РЭБ | ● | ● | ● | — | многоканальные CRPA-приёмники | — | [CSIS](https://www.csis.org/analysis/drone-saturation-russias-shahed-campaign), [Focus](https://focus.ua/uk/eksklyuzivy/728546-efektivnist-mobilnih-vognevih-grup-skilki-naspravdi-zbivayut-shahediv) `[НЕ ВЕРИФИЦИРОВАНО]` |
| Лазер / СВЧ | — | ○ | ● | — | погода, мощность, время на цель | DragonFire ~£10/выстрел; Epirus $66 млн | [GOV.UK](https://www.gov.uk/government/news/boost-for-armed-forces-as-new-laser-weapon-takes-down-high-speed-drones), [Epirus](https://www.epirusinc.com/news-item/us-army-awards-epirus-661m-contract-for-leonidas-directed-energy-system) |
| Сети (перехватчик с сетью, сетчатые турели, антидроновые сетки над зданиями) | — | — | ● | ● | малый радиус | — | [ParaZero](https://parazero.com/2025/07/28/parazero-successfully-completes-field-trial-of-new-configuration-of-the-defendair-system-offering-a-comprehensive-counter-drone-solution/), [openbelgorod](https://openbelgorod.ru/news/safety/2025-08-26/v-shkolah-belgoroda-poyavyatsya-otvetstvennye-za-opoveschenie-ob-ugroze-ataki-dronov-463478) |
| Оповещение, укрытия, учения | — | — | — | ● основной | дисциплина, ночь, связь | — | [T5](L1_Raw_Data/daily_digest/2026-10-25_T5_Civil_Protection.md) |

● — основной эшелон, ○ — вспомогательный. Классификация — интерпретация команды по источникам, не данные производителей.

**Вывод по матрице.** Ни одно средство не перекрывает все эшелоны; связывает их только C2 + шлюз с общими форматами (SAPIENT/BSI Flex 335, STANREC 4869, C2SIM для симуляции) — подтверждение центрального тезиса концепции. Новое по сравнению с концепцией: **объектовый эшелон** (оповещение и укрытие) — единственный, которым гражданский объект владеет сам.

## Логистика

- **Срок развёртывания** как метрика продукта (цель Эксперта — 24 ч на район R~10 км) пока не подкреплена публичными бенчмарками `[НЕ ВЕРИФИЦИРОВАНО]` (MH-022). Ориентиры по отдельным элементам: привязной дрон в воздухе <2 мин ([Elistair](https://elistair.com/solutions/tethered-dronebox-khronos/)); drone-in-a-box открывается <30 с ([BMDS](https://bm-ds.com/systems/dp-100/)), Skydio Dock — взлёт <20 с ([Army Recognition](https://www.armyrecognition.com/archives/archives-aerospace-defense/defense-news-aerospace-2025/dsei-2025-autonomous-skydio-dock-for-x10-expands-us-police-emergency-response-and-infrastructure-security)).
- **Автономность датчиков:** армейский SBIR требует ≥2 недель автономного питания для пассивного узла ([Army SBIR](https://armysbir.army.mil/topics/low-altitude-passive-detection-system/)).
- **Сетка акустики R=10 км:** ~40 узлов при шаге 3 км [расчёт, см. 05].
- **Люди:** в Украине для перехватчиков нужно «3 на «Шахед»», ~2500/сутки ([dev.ua](https://dev.ua/en/news/sting-2100-1759409744)); 400 операторов на 400 целей ([ТСН](https://tsn.ua/ato/matematyka-viyny-chomu-perekhopliuvaty-shakhedy-ne-naykrashche-rishennia-2869841.html)). Кадровый контур — отдельная логистическая статья.
- **Аэростаты:** экипаж, гелий, погодные окна; малые аэростаты не работают в сильный ветер ([DHS](https://www.dhs.gov/sites/default/files/publications/TetheredAerostat_AppN_0913-508.pdf), [CU white paper](https://www.carolinaunmanned.com/_files/ugd/433ce5_a9abc57cfca8435c81767a7885e7b06a.pdf)).

## Экономика

| Пара «атака / оборона» | Цена атаки | Цена обороны | Соотношение | Источник |
|---|---|---|---|---|
| «Шахед» / ракета Patriot | $20–50 тыс. | ~$4 млн | атака дешевле в ~80–200 раз | [CSIS](https://www.csis.org/analysis/drone-saturation-russias-shahed-campaign), [Politico](https://www.politico.eu/article/war-in-ukraine-interceptor-drones-russia-shahed-drones/) |
| «Шахед» / перехватчик Sting | ~$35 тыс. | $2100 × 3 = ~$6300 | оборона дешевле ~в 5,5 раз | [dev.ua](https://dev.ua/en/news/sting-2100-1759409744) |
| «Шахед» / перехватчики (оценка Касьянова) | ~$80 тыс. | $10 тыс. (день) – $40 тыс. (ночь) | ~1:2…1:8 | [ТСН](https://tsn.ua/ato/matematyka-viyny-chomu-perekhopliuvaty-shakhedy-ne-naykrashche-rishennia-2869841.html) |
| «Шахед» / 35-мм Gepard | $20–50 тыс. | ~$600/снаряд, «несколько тыс. $» за поражение | оборона дешевле | [Euromaidan Press](https://euromaidanpress.com/2025/07/20/ukraine-drone-defense/) |
| «Шахед» / лазер DragonFire | $20–50 тыс. | ~£10/выстрел (без цены комплекса) | — | [GOV.UK](https://www.gov.uk/government/news/boost-for-armed-forces-as-new-laser-weapon-takes-down-high-speed-drones) |

Расхождение цены «Шахеда» ($20–80 тыс.) зафиксировано в [MH-021](Model_Health.md). Главный экономический вывод: **цена одного перехвата вторична по отношению к глубине запаса и людям** — при волнах важно, сколько перехватов система может сделать подряд и сколько стоит пропущенная цель. Отсюда правило Эксперта «дешёвое средство первым, дорогое — если цель прошла» и роль C2, которая это правило исполняет.

## Бэклог исследований

Задачи Эксперта из второго разговора и новые задачи этого цикла — в [governance/RESEARCH_BACKLOG.md](governance/RESEARCH_BACKLOG.md).

## Источники (L1)

См. ссылки на L1-записи в начале документа; все внешние ссылки продублированы в соответствующих дайджестах L1.

---
См. [мастер-индекс](00_Index_Master.md).
