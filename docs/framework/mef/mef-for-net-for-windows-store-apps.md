---
title: "MEF для .NET для магазина Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8436bff3b6ca1061621a67eb45bdc8aedea33f2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="eb608-102">MEF для .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="eb608-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="eb608-103"><xref:System.Composition?displayProperty=nameWithType>и его дочерние пространства имен содержат типы для разработки расширяемого [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="eb608-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="eb608-104">Эти пространства имен являются частью [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] подмножества для [!INCLUDE[win8](../../../includes/win8-md.md)] операционной системы.</span><span class="sxs-lookup"><span data-stu-id="eb608-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="eb608-105">Эти пространства имен не входят в основную библиотеку классов, распространяемой с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb608-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="eb608-106">Чтобы установить следующие пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** из **проекта** меню и найдите пакет Microsoft.Composition в Интернете.</span><span class="sxs-lookup"><span data-stu-id="eb608-106">To install these namespaces, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="eb608-107"><xref:System.Composition?displayProperty=nameWithType>предоставляет классы, которые составляют ядро MEF для [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="eb608-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="eb608-108"><xref:System.Composition.Convention?displayProperty=nameWithType>Предоставляет типы, поддерживающие благодаря применению MEF модель конфигурации на основе соглашений.</span><span class="sxs-lookup"><span data-stu-id="eb608-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="eb608-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>Предоставляет типы MEF, которые полезны для разработчиков, ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="eb608-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="eb608-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>Предоставляет типы MEF внутреннего использования подсистемой композиции.</span><span class="sxs-lookup"><span data-stu-id="eb608-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="eb608-111">Дополнительные сведения о [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и просмотреть список пространств имен и типов, содержащихся в нем [Обзор приложений .NET для магазина Windows](http://go.microsoft.com/fwlink/p/?LinkID=238312) в центре разработчиков Windows.</span><span class="sxs-lookup"><span data-stu-id="eb608-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb608-112">См. также</span><span class="sxs-lookup"><span data-stu-id="eb608-112">See Also</span></span>  
 [<span data-ttu-id="eb608-113">Обзор приложений .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="eb608-113">.NET for Windows Store apps overview</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="eb608-114">Поддерживаемые API .NET для приложений Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="eb608-114">.NET for Windows Store apps – supported APIs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="eb608-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="eb608-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
