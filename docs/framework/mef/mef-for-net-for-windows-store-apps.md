---
title: 'Managed Extensibility Framework для .NET: приложения из магазина Windows Store'
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b62e6fea6da46e6307b35dd1c3372420dced80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648512"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="041e3-102">Managed Extensibility Framework для .NET: приложения из магазина Windows Store</span><span class="sxs-lookup"><span data-stu-id="041e3-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="041e3-103">Пространство имен <xref:System.Composition?displayProperty=nameWithType> и его дочерние пространства содержат типы для разработки расширяемых приложений для [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с использованием Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="041e3-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="041e3-104">Эти пространства имен являются частью подмножества [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] для операционной системы [!INCLUDE[win8](../../../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="041e3-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="041e3-105">Они не входят в состав основной библиотеки классов, распространяемой с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="041e3-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="041e3-106">Чтобы установить эти пространства имен, откройте проект в Visual Studio, выберите пункт **Управление пакетами NuGet** в меню **Проект** и найдите в Интернете пакет Microsoft.Composition.</span><span class="sxs-lookup"><span data-stu-id="041e3-106">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
- <span data-ttu-id="041e3-107"><xref:System.Composition?displayProperty=nameWithType> предоставляет классы, которые составляют ядро MEF для приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="041e3-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
- <span data-ttu-id="041e3-108"><xref:System.Composition.Convention?displayProperty=nameWithType> предоставляет типы, поддерживающие использование MEF с моделью конфигурации на основе соглашений.</span><span class="sxs-lookup"><span data-stu-id="041e3-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
- <span data-ttu-id="041e3-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> предоставляет типы MEF, которые могут пригодиться разработчикам ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="041e3-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
- <span data-ttu-id="041e3-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> предоставляет типы MEF, которые использует обработчик композиции.</span><span class="sxs-lookup"><span data-stu-id="041e3-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="041e3-111">Дополнительные сведения о платформе [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и список входящих в нее пространств имен и типов см. в статье [Обзор приложений .NET для Магазина Windows](https://go.microsoft.com/fwlink/p/?LinkID=238312) в Центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="041e3-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](https://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="041e3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="041e3-112">See also</span></span>

- [<span data-ttu-id="041e3-113">Общие сведения о платформе .NET для приложений Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="041e3-113">.NET for Windows Store apps overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=238312)
- [<span data-ttu-id="041e3-114">Поддерживаемые API .NET для приложений Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="041e3-114">.NET for Windows Store apps – supported APIs</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=247912)
- [<span data-ttu-id="041e3-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="041e3-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
