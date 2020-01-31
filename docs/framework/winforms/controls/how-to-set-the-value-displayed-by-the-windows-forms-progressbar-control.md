---
title: Установка значения, отображаемого элементом управления ProgressBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 79ce1e576652d00b323d31dfc6551e168ea0a9a0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743800"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="9f48f-102">Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f48f-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9f48f-103">Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="9f48f-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9f48f-104">.NET Framework предоставляет несколько различных способов отобразить заданное значение в элементе управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="9f48f-105">Выбор способа зависит от поставленной задачи или от решаемой проблемы.</span><span class="sxs-lookup"><span data-stu-id="9f48f-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="9f48f-106">В следующей таблице показаны подходы, которые можно выбрать.</span><span class="sxs-lookup"><span data-stu-id="9f48f-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="9f48f-107">Подход</span><span class="sxs-lookup"><span data-stu-id="9f48f-107">Approach</span></span>|<span data-ttu-id="9f48f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="9f48f-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9f48f-109">Установите значение элемента управления <xref:System.Windows.Forms.ProgressBar> напрямую.</span><span class="sxs-lookup"><span data-stu-id="9f48f-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="9f48f-110">Этот подход удобен для задач, где известно общее количество элементов, которые будут задействованы, например чтение записей из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9f48f-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="9f48f-111">Кроме того, если необходимо задать значение только один раз или дважды, это легко сделать.</span><span class="sxs-lookup"><span data-stu-id="9f48f-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="9f48f-112">Наконец, используйте этот процесс, если необходимо уменьшить значение, отображаемое индикатором выполнения.</span><span class="sxs-lookup"><span data-stu-id="9f48f-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="9f48f-113">Увеличение <xref:System.Windows.Forms.ProgressBar> отображение фиксированным значением.</span><span class="sxs-lookup"><span data-stu-id="9f48f-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="9f48f-114">Этот подход удобен при отображении простого счетчика между минимальным и максимальным значением, например прошедшее время или числом файлов, которые были обработаны из известного итога.</span><span class="sxs-lookup"><span data-stu-id="9f48f-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="9f48f-115">Увеличение <xref:System.Windows.Forms.ProgressBar> отображается в зависимости от значения.</span><span class="sxs-lookup"><span data-stu-id="9f48f-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="9f48f-116">Этот подход удобен, если необходимо изменить отображаемое значение на несколько раз в разных объемах.</span><span class="sxs-lookup"><span data-stu-id="9f48f-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="9f48f-117">Пример показывает объем занятого места на жестком диске при записи ряда файлов на диск.</span><span class="sxs-lookup"><span data-stu-id="9f48f-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="9f48f-118">Самым прямым способом задания значения, отображаемого индикатором выполнения, является установка свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="9f48f-119">Это можно сделать либо во время разработки, либо во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9f48f-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="9f48f-120">Установка значения ProgressBar напрямую</span><span class="sxs-lookup"><span data-stu-id="9f48f-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="9f48f-121">Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="9f48f-122">В коде задайте для свойства <xref:System.Windows.Forms.ProgressBar.Value%2A> элемента управления целочисленное значение между минимальным и максимальным значениями.</span><span class="sxs-lookup"><span data-stu-id="9f48f-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9f48f-123">Если задать свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> за пределами границ, заданных свойствами <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>, то элемент управления вызывает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="9f48f-124">В следующем примере кода показано, как задать значение <xref:System.Windows.Forms.ProgressBar> напрямую.</span><span class="sxs-lookup"><span data-stu-id="9f48f-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="9f48f-125">Код считывает записи из источника данных и обновляет индикатор выполнения и метку при каждом считывании записи данных.</span><span class="sxs-lookup"><span data-stu-id="9f48f-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="9f48f-126">Для этого примера требуется, чтобы в форме был элемент управления <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.ProgressBar> элемент управления и таблица данных со строкой, именуемой `CustomerRow` с `FirstName` и `LastName` полями.</span><span class="sxs-lookup"><span data-stu-id="9f48f-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     Если отображается ход выполнения с фиксированным интервалом, можно задать значение и затем вызвать метод, который увеличивает значение <xref:System.Windows.Forms.ProgressBar> элемента управления на этот интервал. <span data-ttu-id="9f48f-128">Это полезно для таймеров и других сценариев, в которых ход выполнения не измеряется в процентах от целого.</span><span class="sxs-lookup"><span data-stu-id="9f48f-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="9f48f-129">Увеличение индикатора выполнения на фиксированное значение</span><span class="sxs-lookup"><span data-stu-id="9f48f-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="9f48f-130">Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="9f48f-131">Задайте для свойства <xref:System.Windows.Forms.ProgressBar.Step%2A> элемента управления целое число, представляющее величину, чтобы увеличить отображаемое значение индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="9f48f-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="9f48f-132">Вызовите метод <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>, чтобы изменить значение, отображаемое на величину, заданную в свойстве <xref:System.Windows.Forms.ProgressBar.Step%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="9f48f-133">В следующем примере кода показано, как индикатор выполнения может поддерживать количество файлов в операции копирования.</span><span class="sxs-lookup"><span data-stu-id="9f48f-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="9f48f-134">В следующем примере, когда каждый файл считывается в память, индикатор выполнения и метка обновляются для отражения общего числа считываемых файлов.</span><span class="sxs-lookup"><span data-stu-id="9f48f-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="9f48f-135">Для этого примера требуется, чтобы в форме был элемент управления <xref:System.Windows.Forms.Label> и элемент управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     Наконец, можно увеличить значение, отображаемое индикатором выполнения, чтобы каждое увеличение было уникальным. <span data-ttu-id="9f48f-137">Это полезно, если вы отслеживаете ряд уникальных операций, например запись файлов различных размеров на жесткий диск или измерение хода выполнения в процентах от целого.</span><span class="sxs-lookup"><span data-stu-id="9f48f-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="9f48f-138">Увеличение индикатора выполнения на динамическое значение</span><span class="sxs-lookup"><span data-stu-id="9f48f-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="9f48f-139">Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="9f48f-140">Вызовите метод <xref:System.Windows.Forms.ProgressBar.Increment%2A>, чтобы изменить значение, отображаемое указанным целым числом.</span><span class="sxs-lookup"><span data-stu-id="9f48f-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="9f48f-141">В следующем примере кода показано, как индикатор выполнения может вычислить, сколько места на диске использовалось во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="9f48f-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="9f48f-142">В следующем примере, когда каждый файл записывается на жесткий диск, индикатор выполнения и метка обновляются с учетом объема доступного места на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="9f48f-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="9f48f-143">Для этого примера требуется, чтобы в форме был элемент управления <xref:System.Windows.Forms.Label> и элемент управления <xref:System.Windows.Forms.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9f48f-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number   
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number   
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example   
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of   
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_   
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number   
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and   
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number   
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example   
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of   
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f48f-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f48f-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="9f48f-145">Общие сведения об элементе управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9f48f-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="9f48f-146">Элемент управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="9f48f-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
