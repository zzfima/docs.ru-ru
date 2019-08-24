---
title: Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: df87f00e6e03de67c3fb1adc28472c96f4a47ef4
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015635"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="0fcf2-102">Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fcf2-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="0fcf2-103">С помощью *простой привязки*можно отобразить один элемент данных, например значение столбца из таблицы набора данных, в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="0fcf2-104">Можно выполнить простую привязку любого свойства элемента управления к значению данных.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="0fcf2-105">Простая привязка элемента управления</span><span class="sxs-lookup"><span data-stu-id="0fcf2-105">To simple-bind a control</span></span>

1. <span data-ttu-id="0fcf2-106">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-106">Connect to a data source.</span></span> <span data-ttu-id="0fcf2-107">Дополнительные сведения см. [в разделе Подключение к источнику данных](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="0fcf2-107">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="0fcf2-108">В Visual Studio выберите элемент управления в форме и откройте окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="0fcf2-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="0fcf2-109">Разверните свойство **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="0fcf2-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="0fcf2-110">Свойства, которые чаще всего связаны, отображаются под свойством **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="0fcf2-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="0fcf2-111">Например, в большинстве элементов управления свойство **Text** является наиболее часто привязанным.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="0fcf2-112">Если свойство, которое требуется привязать, не является одним из часто связанных свойств, нажмите кнопку **с многоточием** (![...) в окно свойств Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) в поле **(дополнительно)** для отображения элемента  **Диалоговое окно «Форматирование и дополнительная привязка** » с полным списком свойств для этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="0fcf2-113">Выберите свойство, которое необходимо привязать, и щелкните стрелку раскрывающегося списка в разделе **Привязка**.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="0fcf2-114">Отобразится список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="0fcf2-115">Разверните источник данных, к которому требуется привязаться, пока не найдете нужный одиночный элемент данных.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="0fcf2-116">Например, при привязке к значению столбца в таблице набора данных разверните имя набора данных, а затем разверните имя таблицы для отображения имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="0fcf2-117">Щелкните имя элемента для привязки.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="0fcf2-118">Если вы работали в диалоговом окне **Форматирование и дополнительная привязка** , нажмите кнопку **ОК** , чтобы вернуться в окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="0fcf2-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="0fcf2-119">Если требуется привязать дополнительные свойства элемента управления, повторите шаги с 3 по 7.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0fcf2-120">Поскольку элементы управления с простой привязкой показывают только один элемент данных, очень часто для включения логики навигации в форму Windows Forms с элементами управления с простой привязкой.</span><span class="sxs-lookup"><span data-stu-id="0fcf2-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fcf2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0fcf2-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="0fcf2-122">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fcf2-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="0fcf2-123">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fcf2-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
