---
title: Визуальное наследование в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
ms.openlocfilehash: 6cf2a7d95f7f6b015c785859b646a5d42f907127
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524417"
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="5fba5-102">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fba5-102">Windows Forms Visual Inheritance</span></span>
<span data-ttu-id="5fba5-103">В некоторых случаях вы можете решить, что проект вызывает форму, похожую на форму, созданную в предыдущем проекте.</span><span class="sxs-lookup"><span data-stu-id="5fba5-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="5fba5-104">Или можете захотеть создать базовую форму с параметрами, например водяным знаком или определенной структурой элементов управления, которые будут затем повторно использоваться в проекте, с каждой итерацией, содержащей изменения в исходном шаблоне формы.</span><span class="sxs-lookup"><span data-stu-id="5fba5-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="5fba5-105">Наследование форм позволяет создать базовую форму, затем наследовать от нее и вносить изменения, сохраняя при этом все необходимые исходные параметры.</span><span class="sxs-lookup"><span data-stu-id="5fba5-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="5fba5-106">Формы производного класса можно создавать программно или с помощью выбора компонентов для визуального наследования.</span><span class="sxs-lookup"><span data-stu-id="5fba5-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fba5-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5fba5-107">In This Section</span></span>  
 [<span data-ttu-id="5fba5-108">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fba5-108">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 <span data-ttu-id="5fba5-109">Указания по созданию наследуемых форм в коде.</span><span class="sxs-lookup"><span data-stu-id="5fba5-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="5fba5-110">Практическое руководство. Наследование форм с помощью диалогового окна выбора наследования</span><span class="sxs-lookup"><span data-stu-id="5fba5-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="5fba5-111">Указания по созданию наследуемых форм с помощью окна выбора компонентов для наследования.</span><span class="sxs-lookup"><span data-stu-id="5fba5-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="5fba5-112">Влияние изменения внешнего вида базовой формы</span><span class="sxs-lookup"><span data-stu-id="5fba5-112">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="5fba5-113">Указания по изменению элементов управления базовой формы и их свойств.</span><span class="sxs-lookup"><span data-stu-id="5fba5-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="5fba5-114">Пошаговое руководство. Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="5fba5-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="5fba5-115">Создание базовой формы Windows Forms и ее компиляция в библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="5fba5-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="5fba5-116">После этого данная библиотека классов импортируется в другой проект и создается новая форма, которая наследуется от базовой формы.</span><span class="sxs-lookup"><span data-stu-id="5fba5-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="5fba5-117">Практическое руководство. Использование свойств Modifiers и GenerateMember</span><span class="sxs-lookup"><span data-stu-id="5fba5-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="5fba5-118">Указания по использованию свойств `GenerateMember` и `Modifiers`, актуальных в случае, когда конструктор Windows Forms создает переменную-член для компонента.</span><span class="sxs-lookup"><span data-stu-id="5fba5-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5fba5-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5fba5-119">Related Sections</span></span>  
 [<span data-ttu-id="5fba5-120">Основы наследования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fba5-120">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="5fba5-121">Описание способов определения классов Visual Basic, которые служат основой для других классов.</span><span class="sxs-lookup"><span data-stu-id="5fba5-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="5fba5-122">class</span><span class="sxs-lookup"><span data-stu-id="5fba5-122">class</span></span>](~/docs/csharp/language-reference/keywords/class.md)  
 <span data-ttu-id="5fba5-123">Описание принципов особенностей классов в C#, в которых разрешено единичное наследование.</span><span class="sxs-lookup"><span data-stu-id="5fba5-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="5fba5-124">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fba5-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="5fba5-125">Перечисление распространенных проблем, возникающих в обработчиках событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="5fba5-125">Lists common issues that arise with event handlers in inherited components</span></span>
