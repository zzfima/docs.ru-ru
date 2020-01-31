---
title: Наследование форм
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: cc3a4cc75fd13e8f193a6920ed5b4a9bc8fd5d74
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743325"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="8222f-102">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8222f-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="8222f-103">Создание новых форм Windows Forms путем наследования базовых форм является удобным способом для дублирования уже созданного, минуя процесс повторного создания формы с нуля каждый раз, когда она необходима.</span><span class="sxs-lookup"><span data-stu-id="8222f-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="8222f-104">Дополнительные сведения о наследовании форм во время разработки с помощью диалогового окна **Выбор компонентов для наследования** и как визуально различать уровни безопасности производных элементов управления см. в разделе [Практическое руководство. Наследование форм с помощью диалогового окна выбора наследования](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="8222f-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8222f-105">Для наследования из формы файл или пространство имен, содержащие эту форму, должны быть встроены в исполняемый файл или библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="8222f-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="8222f-106">Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.</span><span class="sxs-lookup"><span data-stu-id="8222f-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="8222f-107">Кроме того необходимо добавить ссылку на пространство имен к классу, наследующему форму.</span><span class="sxs-lookup"><span data-stu-id="8222f-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="8222f-108">Наследовать форму программным способом</span><span class="sxs-lookup"><span data-stu-id="8222f-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="8222f-109">В классе добавьте ссылку на пространство имен, содержащее форму, которую вы хотите наследовать.</span><span class="sxs-lookup"><span data-stu-id="8222f-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="8222f-110">В определении класса добавьте ссылку на форму для наследования.</span><span class="sxs-lookup"><span data-stu-id="8222f-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="8222f-111">Ссылка должна содержать пространство имен, в котором содержится форма, точку, а затем имя базовой формы.</span><span class="sxs-lookup"><span data-stu-id="8222f-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="8222f-112">При наследовании форм следует помнить, что могут возникнуть проблемы с обработчиками событий, которые вызываются дважды, так как каждое событие обрабатывается базовым классом и производным классом.</span><span class="sxs-lookup"><span data-stu-id="8222f-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="8222f-113">Дополнительные сведения о том, как избежать этой проблемы, см. в разделе [Устранение неполадок, связанных с унаследованными обработчиками событий в Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="8222f-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8222f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8222f-114">See also</span></span>

- [<span data-ttu-id="8222f-115">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="8222f-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="8222f-116">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="8222f-116">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="8222f-117">using</span><span class="sxs-lookup"><span data-stu-id="8222f-117">using</span></span>](../../../csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="8222f-118">Влияние изменения внешнего вида базовой формы</span><span class="sxs-lookup"><span data-stu-id="8222f-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="8222f-119">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8222f-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
