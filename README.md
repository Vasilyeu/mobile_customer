# mobile_customer
Forecasting the outflow of clients of the mobile operator

Значения полей в наборах train.csv  и test.csv

'USER_ID' – идентификатор абонента,

ACT_DATE' – дата активации абонента,

'STATUS' – код текущего статуса абонента,

'TP_CURRENT' – код тарифного плана абонента,

'TP_CHANGES_NUM' – количество смен тарифного плана абонентом,

'START_PACK' – тип подключения абонента, обычный (в центре обслуживания) или через промо-канал (предложение о подключении в общественных местах, обычно с бонусами),

'OFFER_GROUP' – тип пакета услуг при подключении, тип Promo значит, что абоненту давались бонусы или скидки на какой-то срок,

'BIRTHDAY' – дата рождения абонента,

'GENDER' – пол абонента,

'MLLS_STATE' – статус участника клуба лояльности компании,

'PORTED_IN' – был ли портирован абонент в сеть из другой сети,

'PORTED_OUT'– был ли портирован абонент из нашей сети когда-нибудь, но потом вернулся обратно,

'OBLIG_NUM' – количество раз, когда абонент покупал в салоне обслуживания оборудование (например, телефон) в рассрочку (от obligations - обязательства),

'OBLIG_ON_START' – покупал ли абонент оборудование в первый свой день прихода в сеть (активации),

'ASSET_TYPE_LAST' – тип последнего купленного оборудования,

'DEVICE_TYPE_BUS' – тип устройства, которым пользуется абонент большую часть своего времени осенью 2016 г (в том, где вставлена сим-карта),

'USAGE_AREA' – тип местности, где абонент проводит в сети большую часть времени осенью 2016 г
(Regional Cities – областные города без Минска, Local Towns – все остальные н.п. со статусом города, Countryside – всё остальное),
'REFILL_OCT_16' – сумма пополнения баланса абонентом в октябре 2016 г. (в старых рублях, BYR),

'REFILL_NOV_16'– сумма пополнения баланса абонентом в ноябре 2016 г. (в старых рублях, BYR),

'OUTGOING_OCT_16' – суммарное количество минут исходящих вызовов в октябре 2016,

'OUTGOING_NOV_16' – суммарное количество минут исходящих вызовов в ноябре 2016,

'GPRS_OCT_16' – суммарный использованный интернет траффик абонента в мегабайтах в октябре 2016,

'GPRS_NOV_16'– суммарный использованный интернет траффик абонента в мегабайтах в ноябре 2016,

'REVENUE_OCT_16' – сумма денег, списанная с баланса абонента в октябре 2016 (новые рубли, BYN)
– за использованный не включённый в тарифный план траффик, абонентская плата, подключение платных услуг и т.д.

'REVENUE_NOV_16' – сумма денег, списанная с баланса абонента в ноябре 2016 (новые рубли, BYN),

'ACTIVITY_DEC_16' – активность абонента в декабре 2016. Под активностью подразумевается любая фактическая сетевая или денежная активность (атрибута нет в test.csv, это target)

Нужно на основании датасета train.csv создать модель, предсказывающую, будет ли абонент активным в декабре 2016 г. (1 или 0)

Если абонент целый месяц не был активным, то с высокой вероятностью он уже больше не вернётся, поэтому нужно заранее пытаться предсказать уход таких абонентов, что Вам и предлагается.

В данных есть естественные пропуски – например, если нет информации об исходящих вызовах абонента, то значит у него их не было. В случаях с рассрочкой, клуба лояльности, портированием и тд – абонент не участвовал в этих мероприятиях.  Тип и местоположение устройства отсутствуют -  не было активности или (реже) не определился телефон. Старт-пак и офер-груп: по техническим причинам нет информации.
