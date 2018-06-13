---
title: Тип &#39; &lt;typename&gt; &#39; не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595190"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="52893-102">Тип &#39; &lt;typename&gt; &#39; не определен</span><span class="sxs-lookup"><span data-stu-id="52893-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="52893-103">Инструкция представляет собой ссылку на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="52893-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="52893-104">Можно определить тип в операторе объявления например `Enum`, `Structure`, `Class`, или `Interface`.</span><span class="sxs-lookup"><span data-stu-id="52893-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="52893-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="52893-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="52893-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="52893-106">To correct this error</span></span>  
  
-   <span data-ttu-id="52893-107">Убедитесь, что определения типа и его ссылки используют написания.</span><span class="sxs-lookup"><span data-stu-id="52893-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="52893-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="52893-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="52893-109">Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.</span><span class="sxs-lookup"><span data-stu-id="52893-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="52893-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="52893-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="52893-111">Если это так, используйте `Global` ключевое слово, чтобы указать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="52893-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="52893-112">Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=nameWithType> тип недоступен, если он не является полностью соответствовать `Global` ключевое слово: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="52893-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="52893-113">Если тип определен, но библиотека объектов или библиотеки типов, в которой определен не зарегистрирован в Visual Basic, щелкните **добавить ссылку** на **проекта** меню, а затем выберите нужный объект Библиотека или библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="52893-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="52893-114">Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52893-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="52893-115">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="52893-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52893-116">См. также</span><span class="sxs-lookup"><span data-stu-id="52893-116">See Also</span></span>  
 [<span data-ttu-id="52893-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52893-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="52893-118">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="52893-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="52893-119">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="52893-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="52893-120">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="52893-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="52893-121">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="52893-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="52893-122">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="52893-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
