---
title: Практическое руководство. Упорядочение дочерних MDI-форм
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: c7a9d03ef60586e1162f088d662dfe44bbdcb591
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317237"
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="fff73-102">Практическое руководство. Упорядочение дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="fff73-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="fff73-103">Во многих случаях приложения будут иметь команды меню для таких действий как «Мозаика», «Каскад» и «Упорядочить», которые позволяют управлять компоновкой открытых дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="fff73-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="fff73-104">Для изменения порядка дочерних форм в родительской MDI-форме можно использовать метод <xref:System.Windows.Forms.Form.LayoutMdi%2A> с одним из значений перечисления <xref:System.Windows.Forms.MdiLayout>.</span><span class="sxs-lookup"><span data-stu-id="fff73-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="fff73-105">Значения перечисления <xref:System.Windows.Forms.MdiLayout> позволяют отображать дочерние формы в виде каскада, мозаично по вертикали или горизонтали, либо в виде значков форм, расположенных в нижней части MDI-формы.</span><span class="sxs-lookup"><span data-stu-id="fff73-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="fff73-106">Эти значения имеют тот же эффект, что команды Windows **каскадом**, **отображать окна рядом**, **отображать окна стопкой**, и **отображает рабочий стол** , соответственно.</span><span class="sxs-lookup"><span data-stu-id="fff73-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="fff73-107">Эти методы часто используются в качестве обработчиков событий, вызываемых с помощью события <xref:System.Windows.Forms.Control.Click> пункта меню.</span><span class="sxs-lookup"><span data-stu-id="fff73-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="fff73-108">Таким образом, пункт меню с текстом «Окна каскадом» может оказать требуемое воздействие на дочерние MDI-окна.</span><span class="sxs-lookup"><span data-stu-id="fff73-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="fff73-109">Упорядочение дочерних форм</span><span class="sxs-lookup"><span data-stu-id="fff73-109">To arrange child forms</span></span>  
  
1. <span data-ttu-id="fff73-110">В методе для родительской MDI-формы используйте перечисление <xref:System.Windows.Forms.Form.LayoutMdi%2A> для задания метода<xref:System.Windows.Forms.MdiLayout>.</span><span class="sxs-lookup"><span data-stu-id="fff73-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="fff73-111">В следующем примере используется значение перечисления <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> для дочерних окон родительской MDI-формы (`Form1`).</span><span class="sxs-lookup"><span data-stu-id="fff73-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="fff73-112">Перечисление используется в коде во время работы обработчика событий для <xref:System.Windows.Forms.Control.Click> событие **Cascade Windows** пункта меню.</span><span class="sxs-lookup"><span data-stu-id="fff73-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fff73-113">Путем изменения значения перечисления <xref:System.Windows.Forms.MdiLayout> можно также мозаично размещать окна и упорядочивать их в виде значков.</span><span class="sxs-lookup"><span data-stu-id="fff73-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2. <span data-ttu-id="fff73-114">В случае использования Visual C# поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fff73-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fff73-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fff73-115">See also</span></span>

- [<span data-ttu-id="fff73-116">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="fff73-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="fff73-117">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="fff73-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="fff73-118">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="fff73-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="fff73-119">Практическое руководство. Определить активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="fff73-119">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="fff73-120">Практическое руководство. Отправки данных в активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="fff73-120">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
