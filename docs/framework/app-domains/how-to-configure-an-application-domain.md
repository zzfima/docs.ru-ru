---
title: "Практическое руководство. Настройка домена приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 890a8b31339715a4dac8fd2c6e76cc11cda0ee4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="83dd5-102">Практическое руководство. Настройка домена приложения</span><span class="sxs-lookup"><span data-stu-id="83dd5-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="83dd5-103">Сведения о настройке нового домена приложения среде CLR можно предоставить с помощью класса <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="83dd5-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="83dd5-104">При создании собственных доменов приложений наиболее важным свойством является <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="83dd5-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="83dd5-105">Другие свойства **AppDomainSetup** используются главным образом узлами среды выполнения для настройки определенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83dd5-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="83dd5-106">Свойство **ApplicationBase** определяет корневой каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="83dd5-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="83dd5-107">Когда среде выполнения требуется разрешить запрос о типе, она выполняет поиск сборки, содержащей тип в каталоге, заданном свойством **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="83dd5-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83dd5-108">Новый домен приложения наследует только свойство **ApplicationBase** своего создателя.</span><span class="sxs-lookup"><span data-stu-id="83dd5-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="83dd5-109">В следующем примере создается экземпляр класса **AppDomainSetup**, используемого для создания домена приложения, производится вывод данных на консоль и затем выгрузка домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83dd5-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83dd5-110">Пример</span><span class="sxs-lookup"><span data-stu-id="83dd5-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="83dd5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="83dd5-111">See Also</span></span>  
 [<span data-ttu-id="83dd5-112">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="83dd5-112">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="83dd5-113">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="83dd5-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
