---
title: Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: f7f1ed2fbca4ab8892cb6c439ae8841fa8828bf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008971"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="0e264-102">Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="0e264-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="0e264-103">С помощью привязки данных Windows Forms можно форматировать данные, отображаемые в элементе управления с привязкой к данным с помощью **форматирование и дополнительная привязка** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="0e264-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e264-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="0e264-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0e264-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="0e264-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0e264-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="0e264-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="0e264-107">Привязка элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="0e264-107">To bind a control and format the displayed data</span></span>  
  
1. <span data-ttu-id="0e264-108">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="0e264-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="0e264-109">Дополнительные сведения см. в разделе [подключение к источнику данных](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="0e264-109">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2. <span data-ttu-id="0e264-110">Выберите элемент управления в форме и откройте окно "Свойства".</span><span class="sxs-lookup"><span data-stu-id="0e264-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3. <span data-ttu-id="0e264-111">Разверните **(DataBindings)** свойства, а затем в **(Дополнительно)** нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](./media/vbellipsesbutton.png " vbEllipsesButton")) для отображения **форматирование и дополнительная привязка** диалоговое окно, имеющая полный список свойств этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0e264-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](./media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4. <span data-ttu-id="0e264-112">Выберите свойство, чтобы привязать и нажмите кнопку **привязки** стрелку.</span><span class="sxs-lookup"><span data-stu-id="0e264-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="0e264-113">Отобразится список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="0e264-113">A list of available data sources is displayed.</span></span>  
  
5. <span data-ttu-id="0e264-114">Разверните источник данных, к которому требуется привязаться, пока не найдете нужный одиночный элемент данных.</span><span class="sxs-lookup"><span data-stu-id="0e264-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="0e264-115">Например, при привязке к значению столбца в таблице набора данных разверните имя набора данных, а затем разверните имя таблицы для отображения имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="0e264-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6. <span data-ttu-id="0e264-116">Щелкните имя элемента для привязки.</span><span class="sxs-lookup"><span data-stu-id="0e264-116">Click the name of an element to bind to.</span></span>  
  
7. <span data-ttu-id="0e264-117">В **формат типа** выберите формат, который следует применить к данным, отображаемым в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="0e264-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="0e264-118">В каждом случае можно указать значение, отображаемое в элементе управления, если источник данных содержит <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="0e264-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="0e264-119">В противном случае параметры будут немного отличаться в зависимости от выбранного типа формата.</span><span class="sxs-lookup"><span data-stu-id="0e264-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="0e264-120">В таблице ниже приведены типы форматов и параметры.</span><span class="sxs-lookup"><span data-stu-id="0e264-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="0e264-121">Тип формата</span><span class="sxs-lookup"><span data-stu-id="0e264-121">Format type</span></span>|<span data-ttu-id="0e264-122">Параметр форматирования</span><span class="sxs-lookup"><span data-stu-id="0e264-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="0e264-123">Без форматирования</span><span class="sxs-lookup"><span data-stu-id="0e264-123">No Formatting</span></span>|<span data-ttu-id="0e264-124">Параметры отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="0e264-124">No options.</span></span>|  
    |<span data-ttu-id="0e264-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="0e264-125">Numeric</span></span>|<span data-ttu-id="0e264-126">Укажите число десятичных разрядов, с помощью **десятичных разрядов** управления "вверх вниз".</span><span class="sxs-lookup"><span data-stu-id="0e264-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e264-127">Валюта</span><span class="sxs-lookup"><span data-stu-id="0e264-127">Currency</span></span>|<span data-ttu-id="0e264-128">Укажите число десятичных разрядов, с помощью **десятичных разрядов** управления "вверх вниз".</span><span class="sxs-lookup"><span data-stu-id="0e264-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e264-129">Дата/время</span><span class="sxs-lookup"><span data-stu-id="0e264-129">Date Time</span></span>|<span data-ttu-id="0e264-130">Выберите способ отображения даты и времени, выбрав один из элементов в **тип** рамка выделения.</span><span class="sxs-lookup"><span data-stu-id="0e264-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="0e264-131">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="0e264-131">Scientific</span></span>|<span data-ttu-id="0e264-132">Укажите число десятичных разрядов, с помощью **десятичных разрядов** управления "вверх вниз".</span><span class="sxs-lookup"><span data-stu-id="0e264-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e264-133">Другой</span><span class="sxs-lookup"><span data-stu-id="0e264-133">Custom</span></span>|<span data-ttu-id="0e264-134">Укажите используемую строку пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="0e264-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="0e264-135">Дополнительные сведения см. в статье [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="0e264-135">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="0e264-136">**Примечание.**  Строки пользовательского формата не гарантируют успешного цикла обработки между источником данных и связанным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="0e264-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="0e264-137">Вместо них в коде обработки событий для привязки и применения пользовательских форматов обрабатывайте событие <xref:System.Windows.Forms.Binding.Parse> или <xref:System.Windows.Forms.Binding.Format>.</span><span class="sxs-lookup"><span data-stu-id="0e264-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8. <span data-ttu-id="0e264-138">Нажмите кнопку **ОК** закрыть **форматирование и дополнительная привязка** диалоговое окно и вернуться в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="0e264-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e264-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0e264-139">See also</span></span>

- [<span data-ttu-id="0e264-140">Практическое руководство. Создание элемента управления простой привязкой в форме Windows</span><span class="sxs-lookup"><span data-stu-id="0e264-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="0e264-141">Проверка введенных пользователем данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e264-141">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="0e264-142">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e264-142">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
