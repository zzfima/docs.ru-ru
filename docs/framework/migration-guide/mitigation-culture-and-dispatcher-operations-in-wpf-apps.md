---
title: "Устранение рисков. Язык и региональные параметры и операции диспетчеризации в приложениях WPF"
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
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="d73b8-102">Устранение рисков. Язык и региональные параметры и операции диспетчеризации в приложениях WPF</span><span class="sxs-lookup"><span data-stu-id="d73b8-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="d73b8-103">В приложениях, предназначенных для .NET Framework 4.6 или .NET Framework 4.6.1, изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные в <xref:System.Windows.Threading.Dispatcher>, теряются при завершении соответствующей операции диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="d73b8-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="d73b8-104">Аналогичным образом, изменения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные за пределами операции диспетчеризации, не будут учитываться при выполнении этой операции.</span><span class="sxs-lookup"><span data-stu-id="d73b8-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="d73b8-105">Это связано с некоторыми изменениями в <xref:System.Threading.ExecutionContext>, в результате которых <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в контексте выполнения.</span><span class="sxs-lookup"><span data-stu-id="d73b8-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="d73b8-106">Операции диспетчеризации WPF сохраняют контекст выполнения, который используется для запуска операции и восстановления предыдущего контекста при завершении операции.</span><span class="sxs-lookup"><span data-stu-id="d73b8-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="d73b8-107">Поскольку <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> теперь являются частью этого контекста, внесенные в рамках операции диспетчеризации изменения не сохраняются вне этой операции.</span><span class="sxs-lookup"><span data-stu-id="d73b8-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d73b8-108">Последствия</span><span class="sxs-lookup"><span data-stu-id="d73b8-108">Impact</span></span>  
 <span data-ttu-id="d73b8-109">Проще говоря, изменения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> не передаются между вызовами пользовательского интерфейса WPF и другим кодом в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="d73b8-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d73b8-110">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="d73b8-110">Mitigation</span></span>  
 <span data-ttu-id="d73b8-111">Для приложений, затронутых этим изменением, есть два решения.</span><span class="sxs-lookup"><span data-stu-id="d73b8-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="d73b8-112">Сохранять нужные значения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> в отдельном поле и проверять во всех операциях <xref:System.Windows.Threading.Dispatcher> (включая обработчики событий вызова пользовательского интерфейса), правильно ли установлены значения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d73b8-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="d73b8-113">Поскольку изменение в <xref:System.Threading.ExecutionContext> затрагивает только приложения WPF, предназначенные для .NET Framework 4.6 или .NET Framework 4.6.1, можно обойти это изменение, нацелив приложение на .NET Framework 4.5.2 или на любую версию выше .NET Framework 4.6.2, включительно.</span><span class="sxs-lookup"><span data-stu-id="d73b8-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73b8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d73b8-114">See Also</span></span>  
 [<span data-ttu-id="d73b8-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="d73b8-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

