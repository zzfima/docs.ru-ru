---
title: Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: ffeecc1dfe52f1703fc201ef196644afbcc4708c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536840"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="8f702-102">Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f702-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="8f702-103">Специальные возможности — это специализированные программы и устройства, помогающие людям с ограниченными возможностями эффективнее использовать компьютеры.</span><span class="sxs-lookup"><span data-stu-id="8f702-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="8f702-104">Примеры: средства чтения с экрана для слепых и служебные программы голосового ввода для людей, использующих голосовые команды вместо мыши и клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="8f702-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="8f702-105">Специальные возможности взаимодействуют со свойствами специальных возможностей, представленными элементами управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8f702-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="8f702-106">К этим свойствам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="8f702-106">These properties are:</span></span>  
  
-   <span data-ttu-id="8f702-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="8f702-107">**AccessibilityObject**</span></span>  
  
-   <span data-ttu-id="8f702-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="8f702-108">**AccessibleDefaultActionDescription**</span></span>  
  
-   <span data-ttu-id="8f702-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="8f702-109">**AccessibleDescription**</span></span>  
  
-   <span data-ttu-id="8f702-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="8f702-110">**AccessibleName**</span></span>  
  
-   <span data-ttu-id="8f702-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="8f702-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="8f702-112">Свойство AccessibilityObject</span><span class="sxs-lookup"><span data-stu-id="8f702-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="8f702-113">Это свойство, доступное только для чтения, содержит экземпляр <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="8f702-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="8f702-114">**AccessibleObject** реализует интерфейс <xref:Accessibility.IAccessible> , предоставляющий описание элементов управления, расположение на экране, возможности навигации и значение.</span><span class="sxs-lookup"><span data-stu-id="8f702-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="8f702-115">Конструктор задает это значение при добавлении элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="8f702-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="8f702-116">Свойство AccessibleDefaultActionDescription</span><span class="sxs-lookup"><span data-stu-id="8f702-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="8f702-117">Эта строка описывает действие элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8f702-117">This string describes the action of the control.</span></span> <span data-ttu-id="8f702-118">Она не отображается в окне "Свойства", и ее можно задать только в коде.</span><span class="sxs-lookup"><span data-stu-id="8f702-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="8f702-119">В следующем примере это свойство задается для элемента управления "Кнопка".</span><span class="sxs-lookup"><span data-stu-id="8f702-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="8f702-120">Свойство AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="8f702-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="8f702-121">Эта строка описывает элемент управления.</span><span class="sxs-lookup"><span data-stu-id="8f702-121">This string describes the control.</span></span> <span data-ttu-id="8f702-122">Его можно задать в окне "Свойства" или в коде следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8f702-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="8f702-123">Свойство AccessibleName</span><span class="sxs-lookup"><span data-stu-id="8f702-123">AccessibleName Property</span></span>  
 <span data-ttu-id="8f702-124">Это имя элемента управления, переданное специальным возможностям.</span><span class="sxs-lookup"><span data-stu-id="8f702-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="8f702-125">Его можно задать в окне "Свойства" или в коде следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8f702-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="8f702-126">Свойство AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="8f702-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="8f702-127">Это свойство, содержащее <xref:System.Windows.Forms.AccessibleRole> , описывает роль пользовательского интерфейса для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8f702-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="8f702-128">Для нового элемента управления задано значение `Default`.</span><span class="sxs-lookup"><span data-stu-id="8f702-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="8f702-129">Это означает, что по умолчанию элемент управления **Кнопка** работает как **Кнопка**.</span><span class="sxs-lookup"><span data-stu-id="8f702-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="8f702-130">Возможно, потребуется сбросить это свойство, если у элемента управления есть другая роль.</span><span class="sxs-lookup"><span data-stu-id="8f702-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="8f702-131">Например, вы можете использовать элемент управления **PictureBox** в качестве **Chart**и вам может потребоваться, чтобы специальные возможности передавали роль как **Chart**, а не как **PictureBox**.</span><span class="sxs-lookup"><span data-stu-id="8f702-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="8f702-132">Возможно, вы захотите указать это свойство для разработанных пользовательских элементов управления.</span><span class="sxs-lookup"><span data-stu-id="8f702-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="8f702-133">Это свойство можно задать в окне "Свойства" или в коде следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8f702-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f702-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8f702-134">See Also</span></span>  
 <xref:System.Windows.Forms.AccessibleObject>  
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.AccessibleRole>
