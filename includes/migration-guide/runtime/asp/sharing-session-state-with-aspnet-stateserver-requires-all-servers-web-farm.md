### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Для совместного доступа к состоянию сеанса с Asp.Net StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework

|   |   |
|---|---|
|Подробные сведения|При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.|
|Предложение|Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|

