---
title: Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: b5ad85a9477ca32cd28f246abe4ece3cace43182
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666774"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="2a4f8-102">Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="2a4f8-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="2a4f8-103">С Windows Forms привязкой данных можно отформатировать данные, отображаемые в элементе управления с привязкой к данным, с помощью диалогового окна **Форматирование и дополнительная привязка** .</span><span class="sxs-lookup"><span data-stu-id="2a4f8-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="2a4f8-104">Привязка элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="2a4f8-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="2a4f8-105">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-105">Connect to a data source.</span></span>

     <span data-ttu-id="2a4f8-106">Дополнительные сведения см. [в разделе Подключение к источнику данных](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="2a4f8-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="2a4f8-107">Выберите элемент управления в форме и откройте окно "Свойства".</span><span class="sxs-lookup"><span data-stu-id="2a4f8-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="2a4f8-108">Разверните свойство **(DataBindings)** , а затем в поле **(дополнительно)** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) для отображения **форматирования и расширенной** Диалоговое окно "привязка", содержащее полный список свойств для этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="2a4f8-109">Выберите свойство, которое необходимо привязать, а затем щелкните стрелку **привязки** .</span><span class="sxs-lookup"><span data-stu-id="2a4f8-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="2a4f8-110">Отобразится список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="2a4f8-111">Разверните источник данных, к которому требуется привязаться, пока не найдете нужный одиночный элемент данных.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="2a4f8-112">Например, при привязке к значению столбца в таблице набора данных разверните имя набора данных, а затем разверните имя таблицы для отображения имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="2a4f8-113">Щелкните имя элемента для привязки.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="2a4f8-114">В поле **тип формата** выберите формат, который нужно применить к данным, отображаемым в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="2a4f8-115">В каждом случае можно указать значение, отображаемое в элементе управления, если источник данных содержит <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="2a4f8-116">В противном случае параметры будут немного отличаться в зависимости от выбранного типа формата.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="2a4f8-117">В таблице ниже приведены типы форматов и параметры.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="2a4f8-118">Тип формата</span><span class="sxs-lookup"><span data-stu-id="2a4f8-118">Format type</span></span>|<span data-ttu-id="2a4f8-119">Параметр форматирования</span><span class="sxs-lookup"><span data-stu-id="2a4f8-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="2a4f8-120">Без форматирования</span><span class="sxs-lookup"><span data-stu-id="2a4f8-120">No Formatting</span></span>|<span data-ttu-id="2a4f8-121">Параметры отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-121">No options.</span></span>|
    |<span data-ttu-id="2a4f8-122">Numeric</span><span class="sxs-lookup"><span data-stu-id="2a4f8-122">Numeric</span></span>|<span data-ttu-id="2a4f8-123">Укажите число десятичных разрядов, используя десятичные разряды для контроля.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="2a4f8-124">Валюта</span><span class="sxs-lookup"><span data-stu-id="2a4f8-124">Currency</span></span>|<span data-ttu-id="2a4f8-125">Укажите число десятичных разрядов, используя десятичные разряды для контроля.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="2a4f8-126">Дата/время</span><span class="sxs-lookup"><span data-stu-id="2a4f8-126">Date Time</span></span>|<span data-ttu-id="2a4f8-127">Выберите, как следует отображать дату и время, выбрав один из элементов в поле выбора **типа** .</span><span class="sxs-lookup"><span data-stu-id="2a4f8-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="2a4f8-128">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="2a4f8-128">Scientific</span></span>|<span data-ttu-id="2a4f8-129">Укажите число десятичных разрядов, используя десятичные разряды для контроля.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="2a4f8-130">Настраиваемый</span><span class="sxs-lookup"><span data-stu-id="2a4f8-130">Custom</span></span>|<span data-ttu-id="2a4f8-131">Укажите используемую строку пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="2a4f8-132">Дополнительные сведения см. в статье [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a4f8-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="2a4f8-133">**Примечание.**  Строки пользовательского формата не гарантируют успешного цикла обработки между источником данных и связанным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="2a4f8-134">Вместо них в коде обработки событий для привязки и применения пользовательских форматов обрабатывайте событие <xref:System.Windows.Forms.Binding.Parse> или <xref:System.Windows.Forms.Binding.Format>.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="2a4f8-135">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Форматирование и дополнительная привязка** и вернуться к окно свойств.</span><span class="sxs-lookup"><span data-stu-id="2a4f8-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a4f8-136">См. также</span><span class="sxs-lookup"><span data-stu-id="2a4f8-136">See also</span></span>

- [<span data-ttu-id="2a4f8-137">Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a4f8-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="2a4f8-138">Проверка введенных пользователем данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a4f8-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="2a4f8-139">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a4f8-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
