---
title: Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e0b0b01a3c6da0680a3ec5fcd591344e04658a37
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917623"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="536c5-102">Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="536c5-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="536c5-103">Иногда может потребоваться изменить тип столбца, который уже был добавлен в элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="536c5-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="536c5-104">Например, может потребоваться изменить типы некоторых столбцов, создаваемых автоматически при привязке элемента управления к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="536c5-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="536c5-105">Это полезно, когда отображаемая таблица содержит столбцы, содержащие внешние ключи, в строках связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="536c5-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="536c5-106">В этом случае может потребоваться заменить столбцы текстового поля, отображающие эти внешние ключи, столбцами поля со списком, которые отображают более осмысленные значения из связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="536c5-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="536c5-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="536c5-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="536c5-108">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="536c5-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="536c5-109">Изменение типа столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="536c5-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="536c5-110">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="536c5-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="536c5-111">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="536c5-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="536c5-112">В сетке **Свойства столбца** задайте `ColumnType` для свойства новый тип столбца.</span><span class="sxs-lookup"><span data-stu-id="536c5-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="536c5-113">`ColumnType` Свойство является свойством, предназначенным только для времени разработки и указывающим класс, представляющий тип столбца.</span><span class="sxs-lookup"><span data-stu-id="536c5-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="536c5-114">Это не фактическое свойство, определенное в классе столбца.</span><span class="sxs-lookup"><span data-stu-id="536c5-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="536c5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="536c5-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <span data-ttu-id="536c5-116">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="536c5-116">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="536c5-117">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="536c5-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
