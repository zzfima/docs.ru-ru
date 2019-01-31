---
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 80a3d31a8a46ce616be2dd2ab27faf0af04876f2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275085"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="db742-102">Тип "\<typename >" не определен</span><span class="sxs-lookup"><span data-stu-id="db742-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="db742-103">Инструкция содержится ссылка на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="db742-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="db742-104">Можно определить тип в операторе объявления таких как `Enum`, `Structure`, `Class`, или `Interface`.</span><span class="sxs-lookup"><span data-stu-id="db742-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="db742-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="db742-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db742-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="db742-106">To correct this error</span></span>  
  
-   <span data-ttu-id="db742-107">Убедитесь, что определение типа и его ссылка используется написания.</span><span class="sxs-lookup"><span data-stu-id="db742-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="db742-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="db742-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="db742-109">Например, если тип находится в другом модуле и был объявлен `Private`, переместите определение типа в модуль ссылки или объявите его `Public`.</span><span class="sxs-lookup"><span data-stu-id="db742-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="db742-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="db742-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="db742-111">Если это так, используйте `Global` ключевое слово для задания полного имени типа.</span><span class="sxs-lookup"><span data-stu-id="db742-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="db742-112">Например, если проект определяет пространство имен с именем `System`, <xref:System.Object?displayProperty=nameWithType> типа невозможен, если он не является полным образом `Global` ключевое слово: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="db742-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="db742-113">Если тип определен, но библиотека объектов или библиотеки типов, в котором он определен, не зарегистрирована в Visual Basic, щелкните **добавить ссылку** на **проекта** меню, а затем выберите соответствующий объект Библиотека или библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="db742-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="db742-114">Убедитесь, что тип в сборке, которая является частью целевого профиля .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db742-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="db742-115">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="db742-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db742-116">См. также</span><span class="sxs-lookup"><span data-stu-id="db742-116">See also</span></span>
- [<span data-ttu-id="db742-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db742-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="db742-118">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="db742-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="db742-119">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="db742-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="db742-120">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="db742-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="db742-121">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="db742-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="db742-122">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="db742-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
