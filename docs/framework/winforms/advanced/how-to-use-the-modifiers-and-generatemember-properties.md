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
ms.openlocfilehash: 277d2bdebc1d3b85efb70510b8acd34ed3a91087
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710801"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="bec30-102">Практическое руководство. Использование свойств Modifiers и GenerateMember</span><span class="sxs-lookup"><span data-stu-id="bec30-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="bec30-103">При размещении компонента в форму Windows, в среде разработки предоставляются два свойства: `GenerateMember` и `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="bec30-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="bec30-104">`GenerateMember` Свойство указывает, когда конструктор Windows Forms создает переменную-член для компонента.</span><span class="sxs-lookup"><span data-stu-id="bec30-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="bec30-105">`Modifiers` Свойство — это модификатор доступа, назначенный этой переменной члена.</span><span class="sxs-lookup"><span data-stu-id="bec30-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="bec30-106">Если значение `GenerateMember` свойство `false`, значение `Modifiers` не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="bec30-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bec30-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="bec30-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bec30-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="bec30-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bec30-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="bec30-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="bec30-110">Для указания, является ли компонент членом формы</span><span class="sxs-lookup"><span data-stu-id="bec30-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="bec30-111">В конструкторе Windows Forms откройте форму.</span><span class="sxs-lookup"><span data-stu-id="bec30-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="bec30-112">Откройте **элементов**и в форме, поместите три <xref:System.Windows.Forms.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="bec30-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="bec30-113">Задайте `GenerateMember` и `Modifiers` свойства для каждого <xref:System.Windows.Forms.Button> управления согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bec30-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="bec30-114">Имя кнопки</span><span class="sxs-lookup"><span data-stu-id="bec30-114">Button name</span></span>|<span data-ttu-id="bec30-115">Значение GenerateMember</span><span class="sxs-lookup"><span data-stu-id="bec30-115">GenerateMember value</span></span>|<span data-ttu-id="bec30-116">Значение модификаторов</span><span class="sxs-lookup"><span data-stu-id="bec30-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="bec30-117">Без изменений</span><span class="sxs-lookup"><span data-stu-id="bec30-117">No change</span></span>|  
  
4.  <span data-ttu-id="bec30-118">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="bec30-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="bec30-119">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="bec30-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="bec30-120">Откройте **Form1** узел и в **редактор кода**откройте **Form1.Designer.vb** или **Form1.Designer.cs** файл.</span><span class="sxs-lookup"><span data-stu-id="bec30-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="bec30-121">Этот файл содержит код, созданный конструктором Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bec30-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="bec30-122">Найдите объявления для содержатся три кнопки.</span><span class="sxs-lookup"><span data-stu-id="bec30-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="bec30-123">В следующем примере кода показаны различия, определяемое `GenerateMember` и `Modifiers` свойства.</span><span class="sxs-lookup"><span data-stu-id="bec30-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="bec30-124">По умолчанию назначается в конструкторе Windows Forms `private` (`Friend` в Visual Basic) модификатор контейнерные элементы управления, такие как <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="bec30-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="bec30-125">Если с основным <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Form> имеет контейнерного элемента управления, он не принимает новые дочерние объекты в наследуемых элементов управления и форм.</span><span class="sxs-lookup"><span data-stu-id="bec30-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="bec30-126">Решение заключается в изменить модификатор элемента управления базового контейнера для `protected` или `public`.</span><span class="sxs-lookup"><span data-stu-id="bec30-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec30-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bec30-127">See also</span></span>
- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="bec30-128">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bec30-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="bec30-129">Пошаговое руководство: Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="bec30-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="bec30-130">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bec30-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
