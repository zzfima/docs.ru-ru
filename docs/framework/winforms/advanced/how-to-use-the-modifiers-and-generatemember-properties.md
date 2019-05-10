---
title: Практическое руководство. Использование свойств Modifiers и GenerateMember
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211278"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="d26c6-102">Практическое руководство. Использование свойств Modifiers и GenerateMember</span><span class="sxs-lookup"><span data-stu-id="d26c6-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="d26c6-103">При размещении компонента в форму Windows, в среде разработки предоставляются два свойства: `GenerateMember` и `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="d26c6-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="d26c6-104">`GenerateMember` Свойство указывает, когда конструктор Windows Forms создает переменную-член для компонента.</span><span class="sxs-lookup"><span data-stu-id="d26c6-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="d26c6-105">`Modifiers` Свойство — это модификатор доступа, назначенный этой переменной члена.</span><span class="sxs-lookup"><span data-stu-id="d26c6-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="d26c6-106">Если значение `GenerateMember` свойство `false`, значение `Modifiers` не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="d26c6-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="d26c6-107">Укажите, является ли компонент членом формы</span><span class="sxs-lookup"><span data-stu-id="d26c6-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="d26c6-108">В Visual Studio, в конструкторе Windows Forms откройте форму.</span><span class="sxs-lookup"><span data-stu-id="d26c6-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="d26c6-109">Откройте **элементов**и в форме, поместите три <xref:System.Windows.Forms.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d26c6-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="d26c6-110">Задайте `GenerateMember` и `Modifiers` свойства для каждого <xref:System.Windows.Forms.Button> управления согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d26c6-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="d26c6-111">Имя кнопки</span><span class="sxs-lookup"><span data-stu-id="d26c6-111">Button name</span></span>|<span data-ttu-id="d26c6-112">Значение GenerateMember</span><span class="sxs-lookup"><span data-stu-id="d26c6-112">GenerateMember value</span></span>|<span data-ttu-id="d26c6-113">Значение модификаторов</span><span class="sxs-lookup"><span data-stu-id="d26c6-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="d26c6-114">Без изменений</span><span class="sxs-lookup"><span data-stu-id="d26c6-114">No change</span></span>|

4. <span data-ttu-id="d26c6-115">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="d26c6-115">Build the solution.</span></span>

5. <span data-ttu-id="d26c6-116">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="d26c6-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="d26c6-117">Откройте **Form1** узел и в **редактор кода**откройте **Form1.Designer.vb** или **Form1.Designer.cs** файл.</span><span class="sxs-lookup"><span data-stu-id="d26c6-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="d26c6-118">Этот файл содержит код, созданный конструктором Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d26c6-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="d26c6-119">Найдите объявления для содержатся три кнопки.</span><span class="sxs-lookup"><span data-stu-id="d26c6-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="d26c6-120">В следующем примере кода показаны различия, определяемое `GenerateMember` и `Modifiers` свойства.</span><span class="sxs-lookup"><span data-stu-id="d26c6-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="d26c6-121">По умолчанию назначается в конструкторе Windows Forms `private` (`Friend` в Visual Basic) модификатор контейнерные элементы управления, такие как <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="d26c6-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="d26c6-122">Если с основным <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Form> имеет контейнерного элемента управления, он не принимает новые дочерние объекты в наследуемых элементов управления и форм.</span><span class="sxs-lookup"><span data-stu-id="d26c6-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="d26c6-123">Решение заключается в изменить модификатор элемента управления базового контейнера для `protected` или `public`.</span><span class="sxs-lookup"><span data-stu-id="d26c6-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d26c6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d26c6-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="d26c6-125">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d26c6-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="d26c6-126">Пошаговое руководство: Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="d26c6-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="d26c6-127">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d26c6-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
