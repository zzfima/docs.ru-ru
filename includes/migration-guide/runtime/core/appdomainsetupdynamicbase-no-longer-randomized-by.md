---
ms.openlocfilehash: 3f553f95941eaf36cf335e9765a670a05bd157f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234294"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase больше не задается случайно с помощью UseRandomizedStringHashAlgorithm

|   |   |
|---|---|
|Подробные сведения|В версиях до .NET Framework 4.6 значение <xref:System.AppDomainSetup.DynamicBase> задавалось случайным образом между доменами приложений или между процессами, если в файле конфигурации приложения был включен UseRandomizedStringHashAlgorithm. Начиная с версии .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> будет возвращать постоянный результат между различными выполняющимися экземплярами приложения и между различными доменами приложений. Динамические основания при этом по-прежнему будут различаться для разных приложений. Это изменение исключает только случайный элемент именования для различных экземпляров одного приложения.|
|Предложение|Обратите внимание, что включение <code>UseRandomizedStringHashAlgorithm</code> не приведет к случайной установке <xref:System.AppDomainSetup.DynamicBase>. Если требуется случайное основание, для его получения необходимо использовать код приложения, а не этот API.|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
