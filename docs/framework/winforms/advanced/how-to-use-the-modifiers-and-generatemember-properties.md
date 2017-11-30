---
title: "Практическое руководство. Использование свойств Modifiers и GenerateMember"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcb79525e557a66ed471bc38dcbdd444d75ba6b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="34fe8-102">Практическое руководство. Использование свойств Modifiers и GenerateMember</span><span class="sxs-lookup"><span data-stu-id="34fe8-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="34fe8-103">При размещении компонента в форме Windows Forms, два свойства предоставляются средой разработки: `GenerateMember` и `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="34fe8-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="34fe8-104">`GenerateMember` Свойство указывает, когда конструктор Windows Forms создает переменную-член для компонента.</span><span class="sxs-lookup"><span data-stu-id="34fe8-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="34fe8-105">`Modifiers` Свойство имеет модификатор доступа, назначенный этой переменной-члена.</span><span class="sxs-lookup"><span data-stu-id="34fe8-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="34fe8-106">Если значение `GenerateMember` свойство `false`, значение `Modifiers` свойство не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="34fe8-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34fe8-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="34fe8-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="34fe8-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="34fe8-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="34fe8-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="34fe8-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="34fe8-110">Чтобы указать, является ли компонент элементом формы</span><span class="sxs-lookup"><span data-stu-id="34fe8-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="34fe8-111">В конструкторе Windows Forms откройте форму.</span><span class="sxs-lookup"><span data-stu-id="34fe8-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="34fe8-112">Откройте **элементов**и поместите в форме три <xref:System.Windows.Forms.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="34fe8-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="34fe8-113">Задать `GenerateMember` и `Modifiers` свойства для каждого <xref:System.Windows.Forms.Button> управления согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="34fe8-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="34fe8-114">Имя кнопки</span><span class="sxs-lookup"><span data-stu-id="34fe8-114">Button name</span></span>|<span data-ttu-id="34fe8-115">Значение GenerateMember</span><span class="sxs-lookup"><span data-stu-id="34fe8-115">GenerateMember value</span></span>|<span data-ttu-id="34fe8-116">Значение модификаторов</span><span class="sxs-lookup"><span data-stu-id="34fe8-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="34fe8-117">Без изменений</span><span class="sxs-lookup"><span data-stu-id="34fe8-117">No change</span></span>|  
  
4.  <span data-ttu-id="34fe8-118">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="34fe8-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="34fe8-119">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="34fe8-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="34fe8-120">Откройте **Form1** узел и в **редактор кода**откройте **Form1.Designer.vb** или **Form1.Designer.cs** файла.</span><span class="sxs-lookup"><span data-stu-id="34fe8-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="34fe8-121">Этот файл содержит код, созданный конструктором Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="34fe8-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="34fe8-122">Найдите объявления для трех кнопок.</span><span class="sxs-lookup"><span data-stu-id="34fe8-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="34fe8-123">В следующем примере кода показаны различия, указанные `GenerateMember` и `Modifiers` свойства.</span><span class="sxs-lookup"><span data-stu-id="34fe8-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="34fe8-124">По умолчанию, конструктор Windows Forms присваивает `private` (`Friend` в Visual Basic) модификатор контейнерных элементов управления, таких как <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="34fe8-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="34fe8-125">Если с основным <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Form> имеет контейнерный элемент управления не будет принимать новые дочерние элементы в наследуемых элементов управления и форм.</span><span class="sxs-lookup"><span data-stu-id="34fe8-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="34fe8-126">Рекомендуется изменить модификатор элемента управления базового контейнера для `protected` или `public`.</span><span class="sxs-lookup"><span data-stu-id="34fe8-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fe8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="34fe8-127">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="34fe8-128">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34fe8-128">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="34fe8-129">Пошаговое руководство. Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="34fe8-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [<span data-ttu-id="34fe8-130">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34fe8-130">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
