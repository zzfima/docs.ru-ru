---
title: "Практическое руководство. Использование пространства имен \"My\" (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56577ff61c3f637c8e5a0969ae75d65d24ddaef7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="a3814-102">Практическое руководство. Использование пространства имен "My" (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a3814-102">How to: Use the My Namespace (C# Programming Guide)</span></span>
<span data-ttu-id="a3814-103">Пространство имен <xref:Microsoft.VisualBasic.MyServices> (`My` в Visual Basic) обеспечивает простой и интуитивно понятный доступ к ряду классов .NET Framework, позволяя создавать код, взаимодействующий с компьютером, приложением, параметрами, ресурсами и т. д.</span><span class="sxs-lookup"><span data-stu-id="a3814-103">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET Framework classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="a3814-104">Пространство имен `MyServices` изначально разработано для Visual Basic, однако может применяться и в приложениях C#.</span><span class="sxs-lookup"><span data-stu-id="a3814-104">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="a3814-105">Дополнительные сведения об использовании пространства имен `MyServices` из Visual Basic см. в разделе [Разработка с использованием пространства имен My](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="a3814-105">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="adding-a-reference"></a><span data-ttu-id="a3814-106">Добавление ссылки</span><span class="sxs-lookup"><span data-stu-id="a3814-106">Adding a Reference</span></span>  
 <span data-ttu-id="a3814-107">Прежде чем использовать классы `MyServices` в решении, необходимо добавить ссылку на библиотеку Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3814-107">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="a3814-108">Добавление ссылки на библиотеку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3814-108">To add a reference to the Visual Basic library</span></span>  
  
1.  <span data-ttu-id="a3814-109">В **обозревателе решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="a3814-109">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="a3814-110">В диалоговом окне **Ссылки** прокрутите список вниз и выберите библиотеку Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="a3814-110">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="a3814-111">Также можно включить следующую строку в раздел `using` в начале программы.</span><span class="sxs-lookup"><span data-stu-id="a3814-111">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     <span data-ttu-id="a3814-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3814-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3814-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a3814-113">Example</span></span>  
 <span data-ttu-id="a3814-114">В этом примере вызываются различные статические методы, содержащиеся в пространстве имен `MyServices`.</span><span class="sxs-lookup"><span data-stu-id="a3814-114">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="a3814-115">Чтобы скомпилировать этот код, необходимо добавить в проект ссылку на библиотеку Microsoft.VisualBasic.DLL.</span><span class="sxs-lookup"><span data-stu-id="a3814-115">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 <span data-ttu-id="a3814-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3814-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span></span>  
  
 <span data-ttu-id="a3814-117">Некоторые классы из пространства имен `MyServices` нельзя вызывать из приложения C#, как, например, несовместимый класс <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>.</span><span class="sxs-lookup"><span data-stu-id="a3814-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="a3814-118">Конкретно в этом случае вместо него можно использовать статические методы из состава <xref:Microsoft.VisualBasic.FileIO.FileSystem> (также входит в библиотеку VisualBasic.dll).</span><span class="sxs-lookup"><span data-stu-id="a3814-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="a3814-119">Например, ниже показано, как дублировать каталог с помощью одного из таких методов:</span><span class="sxs-lookup"><span data-stu-id="a3814-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 <span data-ttu-id="a3814-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3814-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3814-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a3814-121">See Also</span></span>  
 <span data-ttu-id="a3814-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3814-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a3814-123">[Пространства имен](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3814-123">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="a3814-124">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="a3814-124">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)

