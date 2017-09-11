---
title: "Практическое руководство. Совместное использование сборки с другими приложениями (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 85117cfdc9b12a93891e89727412a03acc83289b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="4a200-102">Практическое руководство. Совместное использование сборки с другими приложениями (C#)</span><span class="sxs-lookup"><span data-stu-id="4a200-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="4a200-103">Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="4a200-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="4a200-104">Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="4a200-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="4a200-105">Предоставление общего доступа к сборке</span><span class="sxs-lookup"><span data-stu-id="4a200-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="4a200-106">Создайте сборку.</span><span class="sxs-lookup"><span data-stu-id="4a200-106">Create your assembly.</span></span> <span data-ttu-id="4a200-107">Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="4a200-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="4a200-108">Назначьте сборке строгое имя.</span><span class="sxs-lookup"><span data-stu-id="4a200-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="4a200-109">Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="4a200-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="4a200-110">Назначьте сведения о версии для сборки.</span><span class="sxs-lookup"><span data-stu-id="4a200-110">Assign version information to your assembly.</span></span> <span data-ttu-id="4a200-111">Дополнительные сведения см. в разделе [Версии сборок](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="4a200-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="4a200-112">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="4a200-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="4a200-113">Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="4a200-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="4a200-114">Получите доступ к типам, содержащимся в сборке, из других приложений.</span><span class="sxs-lookup"><span data-stu-id="4a200-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="4a200-115">Дополнительные сведения см. в разделе [Практическое руководство. Создание ссылки на сборку со строгим именем](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="4a200-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a200-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4a200-116">See Also</span></span>  
 <span data-ttu-id="4a200-117">[Руководство по программированию на C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a200-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4a200-118">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="4a200-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)

