---
title: Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300480"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="425dd-102">Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="425dd-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="425dd-103">Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="425dd-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="425dd-104">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет несколько способов для отображения значения, заданного в <xref:System.Windows.Forms.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="425dd-104">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="425dd-105">Какой подход вы выберете будет зависеть от поставленной задачи или проблема, которую вы пытаетесь решить.</span><span class="sxs-lookup"><span data-stu-id="425dd-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="425dd-106">В следующей таблице показаны подходы, доступные для выбора.</span><span class="sxs-lookup"><span data-stu-id="425dd-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="425dd-107">Подход</span><span class="sxs-lookup"><span data-stu-id="425dd-107">Approach</span></span>|<span data-ttu-id="425dd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="425dd-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="425dd-109">Установите для параметра <xref:System.Windows.Forms.ProgressBar> напрямую управлять.</span><span class="sxs-lookup"><span data-stu-id="425dd-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="425dd-110">Этот подход полезен для выполнения задач, когда вы знаете общее количество элементов, используемых, например, при считывании записей из источника данных.</span><span class="sxs-lookup"><span data-stu-id="425dd-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="425dd-111">Кроме того Если требуется только один или два раза значение, это простой способ сделать это.</span><span class="sxs-lookup"><span data-stu-id="425dd-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="425dd-112">Используйте этот процесс и, наконец, в том случае, если необходимо уменьшить значение, отображаемое по индикатор хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="425dd-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="425dd-113">Увеличить <xref:System.Windows.Forms.ProgressBar> отображения фиксированным значением.</span><span class="sxs-lookup"><span data-stu-id="425dd-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="425dd-114">Этот подход полезен при отображении простой счетчик между минимальной и максимальной, такие как время, затраченное или количество файлов, которые были обработаны из известного общего.</span><span class="sxs-lookup"><span data-stu-id="425dd-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="425dd-115">Увеличить <xref:System.Windows.Forms.ProgressBar> отображения, значение которого изменяется.</span><span class="sxs-lookup"><span data-stu-id="425dd-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="425dd-116">Этот подход полезен в тех случаях, когда вам нужно изменить отображаемое значение несколько раз в разных суммы.</span><span class="sxs-lookup"><span data-stu-id="425dd-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="425dd-117">Пример будет отображаться объем места на жестком диске, использованное при записи набора файлов на диск.</span><span class="sxs-lookup"><span data-stu-id="425dd-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="425dd-118">— Самый простой способ задать значение, отображаемое индикатором, задав <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="425dd-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="425dd-119">Это можно сделать во время разработки или во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="425dd-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="425dd-120">Чтобы задать значение элемента управления ProgressBar напрямую</span><span class="sxs-lookup"><span data-stu-id="425dd-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="425dd-121">Задайте <xref:System.Windows.Forms.ProgressBar> элемента управления <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> значения.</span><span class="sxs-lookup"><span data-stu-id="425dd-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="425dd-122">В коде, задайте в качестве <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство в целочисленное значение между минимальным и максимальным значениями установки.</span><span class="sxs-lookup"><span data-stu-id="425dd-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="425dd-123">Если задать <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство за пределами диапазона, установленного <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> свойства, элемент управления создает <xref:System.ArgumentException> исключение.</span><span class="sxs-lookup"><span data-stu-id="425dd-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="425dd-124">В следующем примере кода показано задание <xref:System.Windows.Forms.ProgressBar> значение напрямую.</span><span class="sxs-lookup"><span data-stu-id="425dd-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="425dd-125">Код считывает записи из источника данных и обновляет индикатор хода выполнения и метки, каждый раз при считывании записи данных.</span><span class="sxs-lookup"><span data-stu-id="425dd-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="425dd-126">В этом примере требуется, что форма содержит <xref:System.Windows.Forms.Label> управления <xref:System.Windows.Forms.ProgressBar> управления и таблицы данных со строкой `CustomerRow` с `FirstName` и `LastName` поля.</span><span class="sxs-lookup"><span data-stu-id="425dd-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     При отображении хода выполнения, который увеличивается с фиксированным интервалом, можно задать значение и затем вызвать метод, увеличивающий <xref:System.Windows.Forms.ProgressBar> элемента управления значение этого интервала. <span data-ttu-id="425dd-128">Это полезно для таймеров и других сценариев, где вы не измеряете хода выполнения в процентах от целого.</span><span class="sxs-lookup"><span data-stu-id="425dd-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="425dd-129">Для увеличения индикатора хода выполнения на фиксированную величину</span><span class="sxs-lookup"><span data-stu-id="425dd-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="425dd-130">Задайте <xref:System.Windows.Forms.ProgressBar> элемента управления <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> значения.</span><span class="sxs-lookup"><span data-stu-id="425dd-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="425dd-131">Задайте в качестве <xref:System.Windows.Forms.ProgressBar.Step%2A> свойство в целое число, представляющее сумму для увеличения индикатора хода выполнения отображается значение.</span><span class="sxs-lookup"><span data-stu-id="425dd-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="425dd-132">Вызовите <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> метод, чтобы изменить значения, отображаемого в, заданного параметром <xref:System.Windows.Forms.ProgressBar.Step%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="425dd-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="425dd-133">В следующем примере кода показано, как индикатор хода выполнения обеспечить число файлов в ходе операции копирования.</span><span class="sxs-lookup"><span data-stu-id="425dd-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="425dd-134">В следующем примере так как каждый файл считывается в память, индикатор хода выполнения и метка они обновлены в соответствии считывания на общее количество файлов.</span><span class="sxs-lookup"><span data-stu-id="425dd-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="425dd-135">В этом примере требуется, что форма содержит <xref:System.Windows.Forms.Label> управления и <xref:System.Windows.Forms.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="425dd-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     Наконец можно увеличить значения, отображенного на индикатор хода выполнения, таким образом, чтобы каждое увеличение уникальным числом. <span data-ttu-id="425dd-137">Это полезно в тех случаях, когда вы отслеживает ряд уникальных операций, таких как запись файлов разных размеров на жесткий диск или измерение хода выполнения в процентах от целого.</span><span class="sxs-lookup"><span data-stu-id="425dd-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="425dd-138">Чтобы увеличить индикатор хода выполнения на динамическое значение</span><span class="sxs-lookup"><span data-stu-id="425dd-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="425dd-139">Задайте <xref:System.Windows.Forms.ProgressBar> элемента управления <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> значения.</span><span class="sxs-lookup"><span data-stu-id="425dd-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="425dd-140">Вызовите <xref:System.Windows.Forms.ProgressBar.Increment%2A> метод, чтобы изменить значения, отображаемого в целое число, указываемое.</span><span class="sxs-lookup"><span data-stu-id="425dd-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="425dd-141">В следующем примере кода показано, как индикатор хода выполнения можно рассчитать, объем дискового пространства, использованного в ходе операции копирования.</span><span class="sxs-lookup"><span data-stu-id="425dd-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="425dd-142">В следующем примере так как каждый файл записывается на жесткий диск, индикатор хода выполнения и метка они обновлены в соответствии объем места на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="425dd-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="425dd-143">В этом примере требуется, что форма содержит <xref:System.Windows.Forms.Label> управления и <xref:System.Windows.Forms.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="425dd-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="425dd-144">См. также</span><span class="sxs-lookup"><span data-stu-id="425dd-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="425dd-145">Общие сведения об элементе управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="425dd-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="425dd-146">Элемент управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="425dd-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
