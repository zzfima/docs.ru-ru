---
title: Настройка проектов и расширение объекта My
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: e6ed43aeff90295f71590bcee180ca1e0f88e5ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330338"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="c224b-102">Настройка проектов и расширение объекта My в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c224b-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="c224b-103">Можно настроить шаблоны проектов для предоставления дополнительных `My` объектов.</span><span class="sxs-lookup"><span data-stu-id="c224b-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="c224b-104">Это облегчает другим разработчикам Поиск и использование объектов.</span><span class="sxs-lookup"><span data-stu-id="c224b-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c224b-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c224b-105">In this section</span></span>

- [<span data-ttu-id="c224b-106">Расширение пространства имен My в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c224b-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="c224b-107">Описывает добавление пользовательских элементов и значений в пространство имен `My` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c224b-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="c224b-108">Упаковка и развертывание пользовательских расширений пространства имен My</span><span class="sxs-lookup"><span data-stu-id="c224b-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="c224b-109">Описание публикации пользовательских расширений пространства имен `My` с помощью шаблонов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c224b-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="c224b-110">Расширение модели приложения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c224b-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="c224b-111">Описывает, как указать собственные расширения для модели приложения путем переопределения членов класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.</span><span class="sxs-lookup"><span data-stu-id="c224b-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="c224b-112">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="c224b-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="c224b-113">Описывает, как управлять тем, какие `My` объекты включены, настроив константу условной компиляции \_MYTYPE для проекта.</span><span class="sxs-lookup"><span data-stu-id="c224b-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c224b-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c224b-114">Related sections</span></span>

- [<span data-ttu-id="c224b-115">Разработка с использованием My</span><span class="sxs-lookup"><span data-stu-id="c224b-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="c224b-116">Описывает, какие объекты `My` доступны в разных типах проектов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c224b-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="c224b-117">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c224b-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="c224b-118">Описание модели Visual Basic для управления поведением Windows Forms приложений.</span><span class="sxs-lookup"><span data-stu-id="c224b-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="c224b-119">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="c224b-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="c224b-120">Описывает, какие объекты `My` доступны в разных типах проектов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c224b-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="c224b-121">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="c224b-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="c224b-122">Описывает, как компилятор использует условную компиляцию для выбора определенных разделов кода для компиляции и исключения других разделов.</span><span class="sxs-lookup"><span data-stu-id="c224b-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="c224b-123">Описывает объект `My`, предоставляющий свойства, методы и события, связанные с текущим приложением.</span><span class="sxs-lookup"><span data-stu-id="c224b-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="c224b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c224b-124">See also</span></span>

- [<span data-ttu-id="c224b-125">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c224b-125">Developing Applications with Visual Basic</span></span>](../index.md)
