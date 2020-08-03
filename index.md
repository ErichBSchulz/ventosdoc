
# Introduction
This is a simple output of the contents of the draft VentOS meta database.

Using YAML files committed git repositories the VentOS project is able to
control changes.

In the future this script will contain various transformation scripts.

*[State](state)* | *[Alarm](alarm)* | *[Alarm Level](alarm_level)* | *[Abbreviation](abbreviation)*

# <a name="state"></a>State (45 items)
LOG_INTERVAL | MAX_LOG_SIZE | ALARM_SUSPEND_DURATION | PATIENT_WEIGHT | PATIENT_HEIGHT | PATIENT_GENDER | IDEAL_BODY_WEIGHT | TV | SET_PI | INSPIRATION_FLOW_TRIGGER | INSPIRATION_P_TRIGGER | EXPIRATORY_TERMINATION_TRIGGER | INSPIRATORY_TIME | MIN_RR | SET_PEEP | SET_FIO2 | VENTILATION_MODE | BATTERY | MAINS | POWER | OXYGEN_LINE | AIR_LINE | TEMPERATURE | P | RR | P1 | P2 | FI | FE | FLOW | FO2 | PCO2 | INSPIRING | PI | PEAK_PI | PEEP | TVI | TVE | MV | FIO2 | FEO2 | ETCO2 | ICO2 | LAST_LOG_TIME | ALARM_SUSPENDED_TIME
|                                | notes                                                                                             | status   | sot       | units       | enum                          |    min |             max | default   |
|:-------------------------------|:--------------------------------------------------------------------------------------------------|:---------|:----------|:------------|:------------------------------|-------:|----------------:|:----------|
| LOG_INTERVAL                   | Desired logging interval                                                                          | draft    | config    | miliseconds | nan                           |    1   |     3.6e+06     | 300000    |
| MAX_LOG_SIZE                   | Maximum log size                                                                                  | draft    | config    | kilobytes   | nan                           |    0   |     4.29497e+09 | 10000     |
| ALARM_SUSPEND_DURATION         | Time that alarms are suspended for by user pressing the "Alarm silence" button.                   | draft    | config    | seconds     | nan                           |   10   |   120           | 60        |
| PATIENT_WEIGHT                 | Patient weight                                                                                    | draft    | operator  | kg          | nan                           |    1   |   500           |           |
| PATIENT_HEIGHT                 | Patient height                                                                                    | draft    | operator  | cm          | nan                           |   15   |   250           |           |
| PATIENT_GENDER                 | Patient gender                                                                                    | draft    | operator  | nan         | ['M', 'F', 'I']               |  nan   |   nan           | I         |
| IDEAL_BODY_WEIGHT              | Ideal body weight                                                                                 | draft    | derived   | kg          | nan                           |    1   |   250           | 70        |
| TV                             | tidal volume [VCV, PRVC]                                                                          | draft    | operator  | ml          | nan                           |  250   |  2000           | 400       |
| SET_PI                         | Pi,  [PSV, PCV]                                                                                   | draft    | operator  | cmH2O       | nan                           |  -10   |    40           | 20        |
| INSPIRATION_FLOW_TRIGGER       | inspiration trigger [PSV]                                                                         | draft    | operator  | ml/minute   | nan                           |  nan   |   nan           | 2         |
| INSPIRATION_P_TRIGGER          | inspiration trigger [PSV]                                                                         | draft    | operator  | cmH2O       | nan                           |    0.1 |    10           | 0.5       |
| EXPIRATORY_TERMINATION_TRIGGER | expiratory termination trigger (percent of peak inspiratory flow) (PSV)                           | draft    | operator  | percent     | nan                           |    0   |    99           | 25        |
| INSPIRATORY_TIME               | inspiratory time (which together with respiratory rate imply IE)                                  | draft    | operator  | miliseconds | nan                           |  100   | 30000           | 2000      |
| MIN_RR                         | In PCV and VCV modes this is the rate, however synchronised modes this value is the minimum rate. | draft    | operator  | BPM         | nan                           |    0   |    60           | 10        |
| SET_PEEP                       | PEEP                                                                                              | draft    | operator  | cmH2O       | nan                           |    0   |    40           | 5         |
| SET_FIO2                       | FiO2                                                                                              | draft    | operator  | percent     | nan                           |   21   |   100           | 50        |
| VENTILATION_MODE               |                                                                                                   | draft    | operator  | nan         | ['VCV', 'PSV', 'PCV', 'PRVC'] |  nan   |   nan           | PSV       |
| BATTERY                        | Battery status                                                                                    | draft    | sensor    | percent     | nan                           |    0   |   100           | nan       |
| MAINS                          | Mains status                                                                                      | draft    | sensor    | Volts       | nan                           |    0   |  1000           | nan       |
| POWER                          | Combined battery and mains power status                                                           | draft    | derived   | percent     | nan                           |    0   |   100           | nan       |
| OXYGEN_LINE                    | Oxygen line pressure                                                                              | draft    | sensor    | mBar        | nan                           |  nan   |   nan           | nan       |
| AIR_LINE                       | Air line pressure                                                                                 | draft    | sensor    | mBar        | nan                           |    0   | 10000           | nan       |
| TEMPERATURE                    | Internal temperature                                                                              | draft    | sensor    | Celsius     | nan                           |    0   |  1000           | nan       |
| P                              | Observed circuit pressure                                                                         | draft    | derived   | cmH2O       | nan                           |    0   |   200           | nan       |
| RR                             |                                                                                                   | draft    | derived   | BPM         | nan                           |    0   |    60           | nan       |
| P1                             | P1                                                                                                | draft    | sensor    | cmH2O       | nan                           |    0   |   200           | nan       |
| P2                             | P2                                                                                                | draft    | sensor    | cmH2O       | nan                           |    0   |   200           | nan       |
| FI                             | flow recorded by the inspiratory manifold sensor                                                  | draft    | sensor    | ml/minute   | nan                           |    0   |   200           | nan       |
| FE                             | flow recorded by the expiratory manifold sensor                                                   | draft    | sensor    | ml/minute   | nan                           |    0   |   200           | nan       |
| FLOW                           | flow recorded by both sensors and smoothed                                                        | draft    | derived   | ml/minute   | nan                           | -200   |   200           | nan       |
| FO2                            | fraction of gas that is oxygen at the patient airway                                              | draft    | sensor    | percent     | nan                           |    0   |   100           | nan       |
| PCO2                           | partial pressure of CO2 measured at the patient airway                                            | draft    | sensor    | mmHg        | nan                           |    0   |   200           | nan       |
| INSPIRING                      | flag to indicate phase of respiratory cycle                                                       | draft    | derived   | Boolean     | nan                           |  nan   |   nan           | nan       |
| PI                             | Pi with some smoothing applied                                                                    | draft    | derived   | cmH2O       | nan                           |    0   |   200           | nan       |
| PEAK_PI                        | Pi                                                                                                | draft    | derived   | cmH2O       | nan                           |    0   |   200           | nan       |
| PEEP                           | PEEP                                                                                              | draft    | derived   | cmH2O       | nan                           |    0   |   200           | nan       |
| TVI                            | TVi                                                                                               | draft    | derived   | ml          | nan                           |    0   |  6000           | nan       |
| TVE                            | TVe                                                                                               | draft    | derived   | ml          | nan                           |    0   |  6000           | nan       |
| MV                             | Minute volume (the product of respiratory rate and tidal volume)                                  | draft    | derived   | ml          | nan                           |    0   | 60000           | nan       |
| FIO2                           | FiO2                                                                                              | draft    | derived   | percent     | nan                           |    0   |   100           | nan       |
| FEO2                           | FeO2                                                                                              | draft    | derived   | percent     | nan                           |    0   |   100           | nan       |
| ETCO2                          | EtCO2                                                                                             | draft    | derived   | mmHg        | nan                           |    0   |   100           | nan       |
| ICO2                           | inspired CO2 partial pressure                                                                     | draft    | derived   | mmHg        | nan                           |    0   |   100           | nan       |
| LAST_LOG_TIME                  | last time the system wrote to the log                                                             | draft    | timestamp | time        | nan                           |  nan   |   nan           | nan       |
| ALARM_SUSPENDED_TIME           | Alarm suspended time                                                                              | draft    | timestamp | time        | nan                           |  nan   |   nan           | nan       |

# <a name="alarm"></a>Alarm (26 items)
BATTERY_LOW | MAINS_LOW | POWER_LOW | OXYGEN_LINE_LOW | AIR_LINE_LOW | PEAK_PI_HI | PI_HI | PI_LOW | PEEP_LOW | TV_LOW | TV_HI | P_DIV | FLOW_DIV | FO2_DIV | MV_HI | MV_LOW | ETCO2_HI | ETCO2_LOW | FIO2_HI | FIO2_LOW | RR_HI | RR_LOW | TV_DIFF | PI_DIFF | RR_DIFF | TEMPERATURE_HI
|                 | notes                                                                                                                      | status   | source                   |
|:----------------|:---------------------------------------------------------------------------------------------------------------------------|:---------|:-------------------------|
| BATTERY_LOW     | Battery status info/warning/alarm/critical (?? % or volts)                                                                 | core     | ['RMVS 1.a']             |
| MAINS_LOW       | Mains power failure (seconds delay)                                                                                        | proposed | ['RMVS 1.a']             |
| POWER_LOW       | Complete loss of power imminent, as both mains and battery unavailable. This is emergency if in mandatory ventilaton mode. | proposed | ['RMVS 1.a', 'RMVS 1.b'] |
| OXYGEN_LINE_LOW | Oxygen supply failure (mBar - eg 3000)                                                                                     | core     | ['RMVS 1.a']             |
| AIR_LINE_LOW    | Air supply failure (mBar - eg 3000)                                                                                        | core     | ['RMVS 1.a']             |
| PEAK_PI_HI      | Instantaneous over-pressure (cmH2O) - a single reading triggers alarm                                                      | core     | ['RMVS 1.c']             |
| PI_HI           | Sustained over-pressure (seconds and cmH2O - eg over 30cmH2O for 5 seconds) - ie a PEEP high alarm                         | proposed | ['RMVS 1.c']             |
| PI_LOW          | Potential disconnect                                                                                                       | core     | ['RMVS 1.d']             |
| PEEP_LOW        | Potential disconnect                                                                                                       | core     | ['RMVS 1.d']             |
| TV_LOW          | Tidal volume low                                                                                                           | core     | ['RMVS 1.d']             |
| TV_HI           | Tidal volume high                                                                                                          | core     | ['RMVS 1.d']             |
| P_DIV           | pressure sensor divergence (fault or miscalibration) cmH2O                                                                 | proposed | ['VentOS']               |
| FLOW_DIV        | flow sensor divergence (fault or miscalibration, ) ml/minute                                                               | proposed | ['VentOS']               |
| FO2_DIV         | oxygen sensor divergence (fault or miscalibration), absolute %                                                             | proposed | ['VentOS']               |
| MV_HI           | minute volume high (ml)                                                                                                    | proposed | ['VentOS']               |
| MV_LOW          | minute volume low (ml)                                                                                                     | proposed | ['VentOS']               |
| ETCO2_HI        | etCO2 high (mmHg)                                                                                                          | proposed | ['VentOS']               |
| ETCO2_LOW       | etCO2 low (mmHg)                                                                                                           | proposed | ['VentOS']               |
| FIO2_HI         | FiO2 low (%)                                                                                                               | proposed | ['VentOS']               |
| FIO2_LOW        | FiO2 low (%)                                                                                                               | proposed | ['VentOS']               |
| RR_HI           | respiratory rate high (BPM)                                                                                                | proposed | ['VentOS']               |
| RR_LOW          | respiratory rate low (BPM) (apnoea) (seconds) (unsigned int)                                                               | proposed | ['VentOS']               |
| TV_DIFF         | tidal volume difference from setting (VCV/PRVC)                                                                            | proposed | ['VentOS']               |
| PI_DIFF         | Pi different from setting (PCV/PSV)                                                                                        | proposed | ['VentOS']               |
| RR_DIFF         | RR difference from setting (BPM)                                                                                           | proposed | ['VentOS']               |
| TEMPERATURE_HI  | overheating (degrees c)                                                                                                    | proposed | ['VentOS']               |

# <a name="alarm_level"></a>Alarm Level (5 items)
NOTICE | ALERT | WARNING | ALARM | CRITICAL
|          | notes                             | synonyms      | status   |
|:---------|:----------------------------------|:--------------|:---------|
| NOTICE   | eg apnoea 10 seconds, battery 10% | ['INFO']      | proposed |
| ALERT    |                                   | ['LOW']       | proposed |
| WARNING  |                                   | ['MEDIUM']    | proposed |
| ALARM    |                                   | ['HIGH']      | proposed |
| CRITICAL |                                   | ['EMERGENCY'] | proposed |

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
