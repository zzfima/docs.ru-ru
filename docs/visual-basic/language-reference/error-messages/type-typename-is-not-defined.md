---
title: "Тип &quot;&lt;typename&gt;&quot; не определен | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 55b76e9d080a2e2e9fe6e9737a713524ea6409f6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="83e85-102">Тип "&lt;typename&gt;" не определен</span><span class="sxs-lookup"><span data-stu-id="83e85-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="83e85-103">Инструкция делает ссылку на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="83e85-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="83e85-104">Можно определить тип в операторе объявления таких как `Enum`, `Structure`, `Class`, или `Interface`.</span><span class="sxs-lookup"><span data-stu-id="83e85-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="83e85-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="83e85-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83e85-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="83e85-106">To correct this error</span></span>  
  
-   <span data-ttu-id="83e85-107">Убедитесь, что определение типа и его ссылка использовать написания.</span><span class="sxs-lookup"><span data-stu-id="83e85-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="83e85-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="83e85-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="83e85-109">Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.</span><span class="sxs-lookup"><span data-stu-id="83e85-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="83e85-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="83e85-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="83e85-111">Если это так, используйте `Global` ключевое слово для полного имени типа.</span><span class="sxs-lookup"><span data-stu-id="83e85-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="83e85-112">Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=fullName>тип недоступен, если он не является полностью соответствовать `Global` ключевое слово: `Global.System.Object`.</xref:System.Object?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="83e85-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=fullName> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="83e85-113">Если тип определен, но библиотека объектов или библиотеки типов, в которой определен не зарегистрирован в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], нажмите кнопку **добавить ссылку** на **проекта** меню и выберите соответствующую библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="83e85-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="83e85-114">Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83e85-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="83e85-115">Дополнительные сведения см. в разделе [Устранение ошибок для различных версий .NET Framework](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="83e85-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e85-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83e85-116">See Also</span></span>  
 <span data-ttu-id="83e85-117">[Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="83e85-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="83e85-118"> [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="83e85-118"> [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="83e85-119"> [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="83e85-119"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="83e85-120"> [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) </span><span class="sxs-lookup"><span data-stu-id="83e85-120"> [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) </span></span>  
<span data-ttu-id="83e85-121"> [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="83e85-121"> [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="83e85-122"> [Управление ссылками в проекте](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span><span class="sxs-lookup"><span data-stu-id="83e85-122"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span></span>
