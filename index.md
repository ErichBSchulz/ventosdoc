
# <a name='top'></a>Introduction
This is a simple output of the contents of the draft VentOS meta database.

Using YAML files committed git repositories the VentOS project is able to
control changes.

In the future this script will contain various transformation scripts.

*[State](#state)* | *[Alarm](#alarm)* | *[Alarm Level](#alarm_level)* | *[Abbreviation](#abbreviation)*

# <a name="state"></a>State (45 items)
LOG_INTERVAL | MAX_LOG_SIZE | ALARM_SUSPEND_DURATION | PATIENT_WEIGHT | PATIENT_HEIGHT | PATIENT_GENDER | IDEAL_BODY_WEIGHT | TV | SET_PI | INSPIRATION_FLOW_TRIGGER | INSPIRATION_P_TRIGGER | EXPIRATORY_TERMINATION_TRIGGER | INSPIRATORY_TIME | MIN_RR | SET_PEEP | SET_FIO2 | VENTILATION_MODE | BATTERY | MAINS | POWER | OXYGEN_LINE | AIR_LINE | TEMPERATURE | P | RR | P1 | P2 | FI | FE | FLOW | FO2 | PCO2 | INSPIRING | PI | PEAK_PI | PEEP | TVI | TVE | MV | FIO2 | FEO2 | ETCO2 | ICO2 | LAST_LOG_TIME | ALARM_SUSPENDED_TIME
|                                | notes                                                                                             | status   | sot       | values                              |
|:-------------------------------|:--------------------------------------------------------------------------------------------------|:---------|:----------|:------------------------------------|
| LOG_INTERVAL                   | Desired interval between writes to system log                                                     | draft    | config    | 300000 (1.0-3600000.0) miliseconds  |
| MAX_LOG_SIZE                   | Maximum log size                                                                                  | draft    | config    | 10000 (0.0-4294967295.0) kilobytes  |
| ALARM_SUSPEND_DURATION         | Time that alarms are suspended for by user pressing the "Alarm silence" button.                   | draft    | config    | 60 (10.0-120.0) seconds             |
| PATIENT_WEIGHT                 | Patient weight                                                                                    | draft    | operator  | (1.0-500.0) kg                      |
| PATIENT_HEIGHT                 | Patient height, required for calculating ideal body weight                                        | draft    | operator  | (15.0-250.0) cm                     |
| PATIENT_GENDER                 | Patient gender, required for calculating ideal body weight                                        | draft    | operator  | I (['M', 'F', 'I'])                 |
| IDEAL_BODY_WEIGHT              | Ideal body weight                                                                                 | draft    | derived   | 70 (1.0-250.0) kg                   |
| TV                             | Desired tidal volume [VCV, PRVC]                                                                  | draft    | operator  | 400 (250.0-2000.0) ml               |
| SET_PI                         | Desired inspiratory pressure (Pi),  [PSV, PCV]                                                    | draft    | operator  | 20 (-10.0-40.0) cmH2O               |
| INSPIRATION_FLOW_TRIGGER       | inspiration trigger [PSV]                                                                         | draft    | operator  | 2 (0.0-10.0) ml/minute              |
| INSPIRATION_P_TRIGGER          | inspiration trigger [PSV]                                                                         | draft    | operator  | 0.5 (0.1-10.0) cmH2O                |
| EXPIRATORY_TERMINATION_TRIGGER | expiratory termination trigger (percent of peak inspiratory flow) (PSV)                           | draft    | operator  | 25 (0.0-99.0) percent               |
| INSPIRATORY_TIME               | inspiratory time (which together with respiratory rate imply IE)                                  | draft    | operator  | 2000 (100.0-30000.0) miliseconds    |
| MIN_RR                         | In PCV and VCV modes this is the rate, however synchronised modes this value is the minimum rate. | draft    | operator  | 10 (0.0-60.0) BPM                   |
| SET_PEEP                       | PEEP                                                                                              | draft    | operator  | 5 (0.0-40.0) cmH2O                  |
| SET_FIO2                       | FiO2                                                                                              | draft    | operator  | 50 (21.0-100.0) percent             |
| VENTILATION_MODE               |                                                                                                   | draft    | operator  | PSV (['VCV', 'PSV', 'PCV', 'PRVC']) |
| BATTERY                        | Battery status                                                                                    | draft    | sensor    | (0.0-100.0) percent                 |
| MAINS                          | Mains electricity power supply status                                                             | draft    | sensor    | (0.0-1000.0) Volts                  |
| POWER                          | Combined battery and mains power status                                                           | draft    | derived   | (0.0-100.0) percent                 |
| OXYGEN_LINE                    | Oxygen supply line pressure                                                                       | draft    | sensor    | (0.0-10000.0) mBar                  |
| AIR_LINE                       | Air supply line pressure                                                                          | draft    | sensor    | (0.0-10000.0) mBar                  |
| TEMPERATURE                    | Internal ventilator temperature                                                                   | draft    | sensor    | (0.0-1000.0) Celsius                |
| P                              | Observed circuit pressure                                                                         | draft    | derived   | (-10.0-200.0) cmH2O                 |
| RR                             | Observed respiratory rate                                                                         | draft    | derived   | (0.0-60.0) BPM                      |
| P1                             | Primary pressure sensor value                                                                     | draft    | sensor    | (-10.0-200.0) cmH2O                 |
| P2                             | Secondary pressure sensor value                                                                   | draft    | sensor    | (-10.0-200.0) cmH2O                 |
| FI                             | Gas flow recorded by the inspiratory manifold sensor                                              | draft    | sensor    | (0.0-200.0) ml/minute               |
| FE                             | Gas flow recorded by the expiratory manifold sensor                                               | draft    | sensor    | (0.0-200.0) ml/minute               |
| FLOW                           | Gas flow recorded by both sensors and smoothed                                                    | draft    | derived   | (-200.0-200.0) ml/minute            |
| FO2                            | Fraction of gas that is oxygen at the patient airway                                              | draft    | sensor    | (0.0-100.0) percent                 |
| PCO2                           | Partial pressure of CO2 measured at the patient airway                                            | draft    | sensor    | (0.0-200.0) mmHg                    |
| INSPIRING                      | flag to indicate phase of respiratory cycle                                                       | draft    | derived   | Boolean                             |
| PI                             | Pi with some smoothing applied                                                                    | draft    | derived   | (0.0-200.0) cmH2O                   |
| PEAK_PI                        | Peak observed pressure                                                                            | draft    | derived   | (0.0-200.0) cmH2O                   |
| PEEP                           | PEEP                                                                                              | draft    | derived   | (0.0-200.0) cmH2O                   |
| TVI                            | TVi                                                                                               | draft    | derived   | (0.0-6000.0) ml                     |
| TVE                            | TVe                                                                                               | draft    | derived   | (0.0-6000.0) ml                     |
| MV                             | Minute volume (the product of respiratory rate and tidal volume)                                  | draft    | derived   | (0.0-60000.0) ml                    |
| FIO2                           | FiO2                                                                                              | draft    | derived   | (0.0-100.0) percent                 |
| FEO2                           | FeO2                                                                                              | draft    | derived   | (0.0-100.0) percent                 |
| ETCO2                          | EtCO2                                                                                             | draft    | derived   | (0.0-100.0) mmHg                    |
| ICO2                           | inspired CO2 partial pressure                                                                     | draft    | derived   | (0.0-100.0) mmHg                    |
| LAST_LOG_TIME                  | last time the system wrote to the log                                                             | draft    | timestamp | time                                |
| ALARM_SUSPENDED_TIME           | Alarm suspended time                                                                              | draft    | timestamp | time                                |

[[top]](#top)

# <a name="alarm"></a>Alarm (26 items)
BATTERY_LOW | MAINS_LOW | POWER_LOW | OXYGEN_LINE_LOW | AIR_LINE_LOW | PEAK_PI_HI | PI_HI | PI_LOW | PEEP_LOW | TV_LOW | TV_HI | P_DIV | FLOW_DIV | FO2_DIV | MV_HI | MV_LOW | ETCO2_HI | ETCO2_LOW | FIO2_HI | FIO2_LOW | RR_HI | RR_LOW | TV_DIFF | PI_DIFF | RR_DIFF | TEMPERATURE_HI
|                 | notes                                                                                                                      | status   | source                   |    min |   max |   default | units     |
|:----------------|:---------------------------------------------------------------------------------------------------------------------------|:---------|:-------------------------|-------:|------:|----------:|:----------|
| BATTERY_LOW     | Battery status info/warning/alarm/critical                                                                                 | core     | ['RMVS 1.a']             |   10   |    90 |        40 | percent   |
| MAINS_LOW       | Mains power failure (seconds delay)                                                                                        | proposed | ['RMVS 1.a']             |   80   |    99 |        90 | Volts     |
| POWER_LOW       | Complete loss of power imminent, as both mains and battery unavailable. This is emergency if in mandatory ventilaton mode. | proposed | ['RMVS 1.a', 'RMVS 1.b'] |   10   |    90 |        40 | percent   |
| OXYGEN_LINE_LOW | Oxygen supply failure (eg 3000)                                                                                            | core     | ['RMVS 1.a']             |  500   |  4000 |      3500 | mBar      |
| AIR_LINE_LOW    | Air supply failure (eg 3000)                                                                                               | core     | ['RMVS 1.a']             |  500   |  4000 |      3500 | mBar      |
| PEAK_PI_HI      | Instantaneous over-pressure - a single reading triggers alarm                                                              | core     | ['RMVS 1.c']             |   20   |    60 |        40 | cmH2O     |
| PI_HI           | Sustained over-pressure (seconds and cmH2O - eg over 30cmH2O for 5 seconds) - ie a PEEP high alarm                         | proposed | ['RMVS 1.c']             |   20   |    60 |        35 | cmH2O     |
| PI_LOW          | Potential disconnect                                                                                                       | core     | ['RMVS 1.d']             |    8   |    35 |        14 | cmH2O     |
| PEEP_LOW        | Potential disconnect                                                                                                       | core     | ['RMVS 1.d']             |    0   |    20 |         2 | cmH2O     |
| TV_LOW          | Tidal volume low ilw                                                                                                       | core     | ['RMVS 1.d']             |  100   |   500 |       300 | ml        |
| TV_HI           | Tidal volume high ilw                                                                                                      | core     | ['RMVS 1.d']             |  400   |  2000 |       800 | ml        |
| P_DIV           | Pressure sensor divergence (fault or miscalibration). This value is quite dependant on smoothing.                          | proposed | ['VentOS']               |    0.1 |    20 |         2 | cmH2O     |
| FLOW_DIV        | Flow sensor divergence (fault, miscalibration, or lead). Dependant on the time this is average overs. ilw                  | proposed | ['VentOS']               |  100   |  2000 |        10 | ml/minute |
| FO2_DIV         | oxygen sensor divergence (fault or miscalibration)                                                                         | proposed | ['VentOS']               |    1   |    20 |        10 | percent   |
| MV_HI           | Minute volume high. Ideally this is interpreted via ideal weight.                                                          | proposed | ['VentOS']               | 1000   | 20000 |     10000 | ml        |
| MV_LOW          | Minute volume low. ilw                                                                                                     | proposed | ['VentOS']               |  400   | 20000 |      2000 | ml        |
| ETCO2_HI        | etCO2 high                                                                                                                 | proposed | ['VentOS']               |   25   |    80 |        50 | mmHg      |
| ETCO2_LOW       | etCO2 low                                                                                                                  | proposed | ['VentOS']               |   20   |    60 |        30 | mmHg      |
| FIO2_HI         | FiO2 low. Ideally this time sensitive, with high FiO2 tolerated briefly.                                                   | proposed | ['VentOS']               |   21   |   100 |        60 | percent   |
| FIO2_LOW        | FiO2 low                                                                                                                   | proposed | ['VentOS']               |   21   |    99 |        25 | percent   |
| RR_HI           | Respiratory rate high. Younger patients may require a higher rate.                                                         | proposed | ['VentOS']               |    8   |    80 |        25 | BPM       |
| RR_LOW          | Respiratory rate low (apnoea) (seconds)                                                                                    | proposed | ['VentOS']               |    6   |    40 |         8 | BPM       |
| TV_DIFF         | Tidal volume difference from setting (VCV/PRVC)                                                                            | proposed | ['VentOS']               |   10   |   400 |       100 | ml        |
| PI_DIFF         | Pi different from setting (PCV/PSV), ie machine did not achieve goal.                                                      | proposed | ['VentOS']               |    1   |    30 |         5 | cmH2O     |
| RR_DIFF         | RR difference from setting                                                                                                 | proposed | ['VentOS']               |    1   |    10 |         5 | BPM       |
| TEMPERATURE_HI  | Overheating                                                                                                                | proposed | ['VentOS']               |   25   |   200 |        70 | Celsius   |

[[top]](#top)

# <a name="alarm_level"></a>Alarm Level (5 items)
NOTICE | ALERT | WARNING | ALARM | CRITICAL
|          | notes                             | synonyms      | status   |
|:---------|:----------------------------------|:--------------|:---------|
| NOTICE   | eg apnoea 10 seconds, battery 10% | ['INFO']      | proposed |
| ALERT    |                                   | ['LOW']       | proposed |
| WARNING  |                                   | ['MEDIUM']    | proposed |
| ALARM    |                                   | ['HIGH']      | proposed |
| CRITICAL |                                   | ['EMERGENCY'] | proposed |

[[top]](#top)

# <a name="abbreviation"></a>Abbreviation (13 items)
BIPAP | CPAP | CMV | ET | Fi | Fi02 | IPPV | MV | PCV | PEEP | PRVC | TV | VCV
|       | full                                       | source   | definition                                                                                                                                                                                                                |
|:------|:-------------------------------------------|:---------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BIPAP | bilevel positive airway pressure           | RMVS     | A non-invasive ventilation mode that provides different levels of pressure when the patient inhales and exhales.                                                                                                          |
| CPAP  | continuous positive airway pressure        | RMVS     | A non-invasive ventilation mode that provides a constant steadypressure to keep the lungs expanded                                                                                                                        |
| CMV   | continuous mandatory ventilation           | RMVS     | nan                                                                                                                                                                                                                       |
| ET    | end-tidal                                  | VentOS   | nan                                                                                                                                                                                                                       |
| Fi    | fraction inspired                          | VentOS   | nan                                                                                                                                                                                                                       |
| Fi02  | fraction of inspired oxygen                | RMVS     | concentration of oxygen in the gas mixture that the patient inhales                                                                                                                                                       |
| IPPV  | intermittent positive pressure ventilation | RMVS     | A mandatory invasive ventilation mode used to replacea patient’sbreathing when they cannot for themselves. Can be either volume controlled or pressure controlled. It does not synchronise any patient breathing efforts. |
| MV    | minute volume                              | VentOS   | nan                                                                                                                                                                                                                       |
| PCV   | pressure controlled ventilation            | RMVS     | nan                                                                                                                                                                                                                       |
| PEEP  | positive end-expiratory pressure           | RMVS     | The pressure maintained in the breathing system during expiration                                                                                                                                                         |
| PRVC  | pressure regulated volume controlled       | RMVS     | A mode of ventilation where a set tidal volume is delivered to the patient while maintain the lowest pressure possible in the airway, to avtrauma.                                                                        |
| TV    | tidal volume                               | VentOS   | nan                                                                                                                                                                                                                       |
| VCV   | volume controlled ventilation              | RMVS     | nan                                                                                                                                                                                                                       |

[[top]](#top)
