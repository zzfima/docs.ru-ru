---
title: Имя <name> не объявлено
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260149"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="68c28-102">Имя "\<имя >" не объявлена</span><span class="sxs-lookup"><span data-stu-id="68c28-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="68c28-103">Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="68c28-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="68c28-104">**Идентификатор ошибки:** BC30451</span><span class="sxs-lookup"><span data-stu-id="68c28-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="68c28-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="68c28-105">To correct this error</span></span>  
  
1. <span data-ttu-id="68c28-106">Проверьте правильность написания в ссылающемся операторе.</span><span class="sxs-lookup"><span data-stu-id="68c28-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="68c28-107">Visual Basic регистр не учитывается, но любое другое изменение в орфографии рассматривается как полностью другое имя.</span><span class="sxs-lookup"><span data-stu-id="68c28-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="68c28-108">Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.</span><span class="sxs-lookup"><span data-stu-id="68c28-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="68c28-109">Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах.</span><span class="sxs-lookup"><span data-stu-id="68c28-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="68c28-110">Например, если у вас есть элемент управления <xref:System.Windows.Forms.TextBox> с именем `TextBox1`, то для доступа к его свойству <xref:System.Windows.Forms.TextBoxBase.Text%2A> следует ввести `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="68c28-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="68c28-111">Если вместо этого ввести `TextBox1Text`, будет создано другое имя.</span><span class="sxs-lookup"><span data-stu-id="68c28-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="68c28-112">Если правильность написания и имеет правильный синтаксис любого доступа к членам объекта, убедитесь, что элемент был объявлен.</span><span class="sxs-lookup"><span data-stu-id="68c28-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="68c28-113">Дополнительные сведения см. в разделе [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="68c28-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="68c28-114">Если программный элемент объявлен, проверьте, что он находится в области.</span><span class="sxs-lookup"><span data-stu-id="68c28-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="68c28-115">Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента.</span><span class="sxs-lookup"><span data-stu-id="68c28-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="68c28-116">Для получения дополнительной информации см. [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="68c28-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="68c28-117">Если вы не используете полное имя типа или типа и имени элемента (например, ваш код ссылается на свойство как `MethodInfo.Name` вместо `System.Reflection.MethodInfo.Name`), добавьте [оператор Imports](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="68c28-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="68c28-118">При попытке компиляции стиле пакетов SDK для проекта (проект с \*VBPROJ-файл, который начинается со строки `<Project Sdk="Microsoft.NET.Sdk">`) и сообщение об ошибке ссылается на тип или член в сборке Microsoft.VisualBasic.dll, Настройка приложения для Компиляция со ссылкой на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="68c28-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="68c28-119">По умолчанию подмножество библиотеки внедряется в сборку в стиле пакетов SDK для проекта.</span><span class="sxs-lookup"><span data-stu-id="68c28-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="68c28-120">Например, в следующем примере выполняется компиляции, поскольку <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> не удается найти метод.</span><span class="sxs-lookup"><span data-stu-id="68c28-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="68c28-121">Он не внедрен в часть среды выполнения Visual Basic, в состав приложения.</span><span class="sxs-lookup"><span data-stu-id="68c28-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   <span data-ttu-id="68c28-122">Чтобы устранить эту ошибку, добавьте `<VBRuntime>Default</VBRuntime>` элемент в проекты `<PropertyGroup>` разделе описано, как показано в следующем файле проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="68c28-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="68c28-123">См. также</span><span class="sxs-lookup"><span data-stu-id="68c28-123">See also</span></span>

- [<span data-ttu-id="68c28-124">Сводка по объявлениям и константам</span><span class="sxs-lookup"><span data-stu-id="68c28-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="68c28-125">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68c28-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="68c28-126">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="68c28-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="68c28-127">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="68c28-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
