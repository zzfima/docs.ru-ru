---
title: "Устранение рисков: язык и региональные параметры и асинхронные операции | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2dbf60cacf47be3c448b5683b771840ef85ddaf
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>Устранение рисков: язык и региональные параметры и асинхронные операции
Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и более поздних версий, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в свойстве <xref:System.Threading.ExecutionContext> потока, который проходит через асинхронные операции.  
  
## <a name="impact"></a>Последствия  
 Это изменение приводит к тому, что изменения в <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> отражаются в задачах, которые впоследствии выполняются асинхронно. Это отличается от поведения предыдущих версий .NET Framework, которые во всех асинхронных задачах сбросили бы <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> до системной настройки по умолчанию.  
  
## <a name="mitigation"></a>Уменьшение  
 Для приложений, затронутых этим изменением, доступны два решения:  
  
-   явно задать нужное свойство <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> как первую операцию в асинхронной задаче;  
  
-   переключиться на прежнее поведение без потока <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, добавив следующий элемент `AppContextSwitchOverrides` в файл конфигурации приложения:  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   переключиться на прежнее поведение без потока <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> путем программной установки следующего переключателя совместимости:  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

