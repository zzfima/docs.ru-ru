---
title: Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 82bab7a42c7a8de131cc53d792cf2d372580af40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078113"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="9f75a-102">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9f75a-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="9f75a-103">Windows Forms <xref:System.Windows.Forms.DataGridView> элемент управления должен содержать столбцы для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="9f75a-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="9f75a-104">Если вы планируете вручную заполнение элемента управления, необходимо добавить столбцы самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="9f75a-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="9f75a-105">Кроме того можно привязать элемент управления к источнику данных, который создает и заполняет столбцы автоматически.</span><span class="sxs-lookup"><span data-stu-id="9f75a-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="9f75a-106">Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.</span><span class="sxs-lookup"><span data-stu-id="9f75a-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="9f75a-107">Следующие процедуры требуют **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9f75a-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9f75a-108">Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9f75a-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f75a-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="9f75a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9f75a-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="9f75a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9f75a-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="9f75a-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="9f75a-112">Чтобы добавить столбец с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9f75a-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="9f75a-113">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="9f75a-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="9f75a-114">В **добавить столбец** диалоговое окно, выберите **с привязкой к данным столбца** параметр и выберите столбец из источника данных или выберите **несвязанного столбца** параметр и для определения столбца с помощью соответствующих полях.</span><span class="sxs-lookup"><span data-stu-id="9f75a-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="9f75a-115">Нажмите кнопку **добавить** кнопка для добавления столбца, который отображается в конструкторе, если существующие столбцы не заполняет область отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9f75a-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f75a-116">Можно изменить свойства столбца в **Правка столбцов** диалоговое окно, к которому можно получить из смарт-тега элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9f75a-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="9f75a-117">Чтобы удалить столбец, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9f75a-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="9f75a-118">Выберите **Правка столбцов** смарт-теге элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9f75a-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="9f75a-119">Выберите столбец из **выбранные столбцы** списка.</span><span class="sxs-lookup"><span data-stu-id="9f75a-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="9f75a-120">Нажмите кнопку **удалить** кнопку, чтобы удалить столбец, чего он исчезнет из конструктора.</span><span class="sxs-lookup"><span data-stu-id="9f75a-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f75a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9f75a-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="9f75a-122">Практическое руководство. Создайте проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f75a-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9f75a-123">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f75a-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
