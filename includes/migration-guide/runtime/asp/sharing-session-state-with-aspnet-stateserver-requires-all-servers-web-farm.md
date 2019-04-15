---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235579"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Для совместного доступа к состоянию сеанса с Asp.Net StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework

|   |   |
|---|---|
|Подробные сведения|При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.|
|Предложение|Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
