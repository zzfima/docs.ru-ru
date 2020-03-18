---
ms.openlocfilehash: 3f553f95941eaf36cf335e9765a670a05bd157f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858463"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase больше не задается случайно с помощью UseRandomizedStringHashAlgorithm

|   |   |
|---|---|
|Подробнее|В версиях до .NET Framework 4.6 значение <xref:System.AppDomainSetup.DynamicBase> задавалось случайным образом между доменами приложений или между процессами, если в файле конфигурации приложения был включен UseRandomizedStringHashAlgorithm. Начиная с версии .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> будет возвращать постоянный результат между различными выполняющимися экземплярами приложения и между различными доменами приложений. Динамические основания при этом по-прежнему будут различаться для разных приложений. Это изменение исключает только случайный элемент именования для различных экземпляров одного приложения.|
|Предложение|Обратите внимание, что включение <code>UseRandomizedStringHashAlgorithm</code> не приведет к случайной установке <xref:System.AppDomainSetup.DynamicBase>. Если требуется случайное основание, для его получения необходимо использовать код приложения, а не этот API.|
|Область|Пограничный случай|
|Version|4.6|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
