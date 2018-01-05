---
title: "Практическое руководство. Использование словаря ресурсов области определения приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece6a5d2123bb118f11940081e3c1d939815a8ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="a6543-102">Практическое руководство. Использование словаря ресурсов области определения приложения</span><span class="sxs-lookup"><span data-stu-id="a6543-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="a6543-103">В этом примере показано, как определить и использовать пользовательский словарь ресурсов области определения приложения.</span><span class="sxs-lookup"><span data-stu-id="a6543-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6543-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a6543-104">Example</span></span>  
 <span data-ttu-id="a6543-105"><xref:System.Windows.Application>предоставляет хранилище области приложения для общих ресурсов: <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6543-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="a6543-106">По умолчанию <xref:System.Windows.Application.Resources%2A> с помощью экземпляра инициализируется свойство <xref:System.Windows.ResourceDictionary> типа.</span><span class="sxs-lookup"><span data-stu-id="a6543-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="a6543-107">Этот экземпляр используется при получение и задание свойств области приложения с помощью <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6543-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="a6543-108">Дополнительные сведения см. в разделе [как: получение и задание ресурсов области приложения](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span><span class="sxs-lookup"><span data-stu-id="a6543-108">For more information, see [How to: Get and Set an Application-Scope Resource](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span></span>
  
 <span data-ttu-id="a6543-109">Если имеется несколько ресурсов, которые можно задать с помощью <xref:System.Windows.Application.Resources%2A>, словарь пользовательских ресурсов вместо этого можно использовать для хранения этих ресурсов и установки <xref:System.Windows.Application.Resources%2A> с ним вместо него.</span><span class="sxs-lookup"><span data-stu-id="a6543-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="a6543-110">Ниже показано, как объявить словарь пользовательских ресурсов с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="a6543-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="a6543-111">Замена целых словарей ресурсов с помощью <xref:System.Windows.Application.Resources%2A> позволяет поддерживать темы области приложения, когда каждая тема инкапсулируется одним словарем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a6543-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="a6543-112">В следующем примере показано, как задать свойство <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="a6543-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="a6543-113">Далее показано, как получить ресурсы области приложения из словаря ресурсов, предоставляемых <xref:System.Windows.Application.Resources%2A> в XAML.</span><span class="sxs-lookup"><span data-stu-id="a6543-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="a6543-114">Ниже показано, как можно получить ресурсы в коде.</span><span class="sxs-lookup"><span data-stu-id="a6543-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="a6543-115">Существуют два аспекта, чтобы сделать при использовании <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6543-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="a6543-116">Во-первых, словарь *ключ* является объектом, поэтому необходимо использовать один и тот же экземпляр объекта при установке и получении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a6543-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="a6543-117">(Обратите внимание, что при использовании строки в ключе учитывается регистр.) Во-вторых, словарь *значение* является объектом, поэтому необходимо преобразовать значение в требуемый тип при получении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a6543-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6543-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a6543-118">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [<span data-ttu-id="a6543-119">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="a6543-119">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="a6543-120">Объединенные словари ресурсов</span><span class="sxs-lookup"><span data-stu-id="a6543-120">Merged Resource Dictionaries</span></span>](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
