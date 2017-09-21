---
title: "Устранение рисков: язык и региональные параметры и асинхронные операции"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>Устранение рисков: язык и региональные параметры и асинхронные операции
Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и более поздних версий, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в свойстве <xref:System.Threading.ExecutionContext> потока, который сохраняется для всех асинхронных операций.  
  
## <a name="impact"></a>Последствия  
 Это изменение приводит к тому, что изменения в <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> отражаются в задачах, которые впоследствии выполняются асинхронно. Это отличается от поведения предыдущих версий .NET Framework, которые во всех асинхронных задачах сбрасывали <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> до системной настройки по умолчанию.  
  
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

