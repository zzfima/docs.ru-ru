---
title: Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 41ab0b36c5f3632ff4458d1289295ab2c9efe7c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420481"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="5bb2a-102">Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5bb2a-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="5bb2a-103">Иногда требуется изменить тип столбца, который уже был добавлен к формам Windows <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5bb2a-104">Например может потребоваться изменить типы некоторых столбцов, которые создаются автоматически при привязке элемента управления к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="5bb2a-105">Это полезно в тех случаях, когда в таблице, которые отображены есть столбцы, содержащие внешние ключи для строк в связанной таблице.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="5bb2a-106">В этом случае необходимо заменить столбцы с текстовыми полями, которые отображают эти внешние ключи, со столбцами поле со списком, отобразить более понятные значения из связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="5bb2a-107">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5bb2a-108">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5bb2a-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bb2a-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5bb2a-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5bb2a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5bb2a-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5bb2a-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="5bb2a-112">Чтобы изменить тип столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5bb2a-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="5bb2a-113">Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **Правка столбцов**.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="5bb2a-114">Выберите столбец из **выбранные столбцы** списка.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="5bb2a-115">В **свойства столбца** сетки, задайте `ColumnType` свойство в новый тип столбца.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bb2a-116">`ColumnType` Свойство является свойством только во время разработки, который указывает класс, представляющий тип столбца.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="5bb2a-117">Это не фактическое свойство, определенное в классе столбца.</span><span class="sxs-lookup"><span data-stu-id="5bb2a-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb2a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb2a-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="5bb2a-119">Практическое: Создание проекта приложения Windows</span><span class="sxs-lookup"><span data-stu-id="5bb2a-119">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="5bb2a-120">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bb2a-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
