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
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="08ff1-102">Устранение рисков: язык и региональные параметры и асинхронные операции</span><span class="sxs-lookup"><span data-stu-id="08ff1-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="08ff1-103">Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и более поздних версий, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в свойстве <xref:System.Threading.ExecutionContext> потока, который сохраняется для всех асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="08ff1-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="08ff1-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="08ff1-104">Impact</span></span>  
 <span data-ttu-id="08ff1-105">Это изменение приводит к тому, что изменения в <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> отражаются в задачах, которые впоследствии выполняются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="08ff1-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="08ff1-106">Это отличается от поведения предыдущих версий .NET Framework, которые во всех асинхронных задачах сбрасывали <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> до системной настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08ff1-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="08ff1-107">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="08ff1-107">Mitigation</span></span>  
 <span data-ttu-id="08ff1-108">Для приложений, затронутых этим изменением, доступны два решения:</span><span class="sxs-lookup"><span data-stu-id="08ff1-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="08ff1-109">явно задать нужное свойство <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> как первую операцию в асинхронной задаче;</span><span class="sxs-lookup"><span data-stu-id="08ff1-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="08ff1-110">переключиться на прежнее поведение без потока <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, добавив следующий элемент `AppContextSwitchOverrides` в файл конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="08ff1-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="08ff1-111">переключиться на прежнее поведение без потока <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> путем программной установки следующего переключателя совместимости:</span><span class="sxs-lookup"><span data-stu-id="08ff1-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="08ff1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="08ff1-112">See Also</span></span>  
 [<span data-ttu-id="08ff1-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="08ff1-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

