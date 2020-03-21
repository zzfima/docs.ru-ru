---
title: Установите значение, отображаемые progressBar Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141815"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms
> [!IMPORTANT]
> Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Рамочность .NET предоставляет несколько различных <xref:System.Windows.Forms.ProgressBar> способов отображения заданного значения в элементе управления. Какой подход вы выберете, будет зависеть от поставленной задачи или от решения проблемы. В следующей таблице показаны подходы, которые вы можете выбрать.  
  
|Подход|Описание|  
|--------------|-----------------|  
|Установите значение <xref:System.Windows.Forms.ProgressBar> элемента управления напрямую.|Этот подход полезен для задач, где вы знаете общее количество измеренного элемента, который будет задействован, например, для чтения записей из источника данных. Кроме того, если вам нужно установить значение только один или два раза, это простой способ сделать это. Наконец, используйте этот процесс, если вам нужно уменьшить значение, отображаемые баром прогресса.|  
|Увеличьте <xref:System.Windows.Forms.ProgressBar> дисплей на фиксированное значение.|Этот подход полезен при отображении простого количества между минимальным и максимальным, например, прошедшее время или количество файлов, которые были обработаны из известного общего числа.|  
|Увеличьте <xref:System.Windows.Forms.ProgressBar> дисплей на значение, которое изменяется.|Этот подход полезен, когда необходимо изменить отображаемые значения несколько раз в разных количествах. Примером может быть отображение количества удерживаемого пространства жесткого диска при написании ряда файлов на диске.|  
  
 Самый прямой способ установить значение, отображаемое панелью прогресса, — это установка <xref:System.Windows.Forms.ProgressBar.Value%2A> свойства. Это может быть сделано либо во время проектирования или во время выполнения.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Установить значение ProgressBar напрямую  
  
1. Установите <xref:System.Windows.Forms.ProgressBar> элемент <xref:System.Windows.Forms.ProgressBar.Minimum%2A> управления <xref:System.Windows.Forms.ProgressBar.Maximum%2A> и значения.  
  
2. В коде установите <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство элемента управления на максимальное значение между установленными минимальными значениями и максимальными значениями.  
  
    > [!NOTE]
    > Если вы <xref:System.Windows.Forms.ProgressBar.Value%2A> установите свойство за <xref:System.Windows.Forms.ProgressBar.Minimum%2A> пределами границ, установленных <xref:System.Windows.Forms.ProgressBar.Maximum%2A> свойствами и свойствами, элемент управления выбрасывает <xref:System.ArgumentException> исключение.  
  
     Следующий пример кода иллюстрирует, <xref:System.Windows.Forms.ProgressBar> как настроить значение напрямую. Код считывает записи из источника данных и обновляет панель прогресса и маркирует каждый раз, когда запись данных читается. Этот пример требует, чтобы <xref:System.Windows.Forms.Label> в <xref:System.Windows.Forms.ProgressBar> вашей форме были элемент управления, `FirstName` `LastName` элемент управления и таблица данных с строкой, с концентрировавающейся `CustomerRow` и полями.  
  
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
  
     Если вы отображаете прогресс, который происходит с фиксированным интервалом, можно установить значение, а затем вызвать метод, который увеличивает значение <xref:System.Windows.Forms.ProgressBar> элемента к этому интервалу. Это полезно для таймеры и других сценариев, где вы не измеряете прогресс в процентах от целого.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Увеличение панели прогресса на фиксированное значение  
  
1. Установите <xref:System.Windows.Forms.ProgressBar> элемент <xref:System.Windows.Forms.ProgressBar.Minimum%2A> управления <xref:System.Windows.Forms.ProgressBar.Maximum%2A> и значения.  
  
2. Установите свойство <xref:System.Windows.Forms.ProgressBar.Step%2A> элемента управления в число, представляющее сумму для увеличения отображаемого значения панели прогресса.  
  
3. Вызовите <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> метод, чтобы изменить значение, отображаемое суммой, установленной в свойстве. <xref:System.Windows.Forms.ProgressBar.Step%2A>  
  
     Следующий пример кода иллюстрирует, как панель прогресса может поддерживать подсчет файлов в операции копирования.  
  
     В следующем примере, когда каждый файл считывается в памяти, панель прогресса и метка обновляются, чтобы отразить общее количество прочитаных файлов. Этот пример требует, чтобы <xref:System.Windows.Forms.Label> ваша <xref:System.Windows.Forms.ProgressBar> форма имеет элемент управления и элемента управления.  
  
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
  
     Наконец, можно увеличить значение, отображаемые баром прогресса, так что каждое увеличение является уникальной суммой. Это полезно, когда вы отслеживаете ряд уникальных операций, таких как написание файлов разных размеров на жесткий диск или измерение прогресса в процентах от целого.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Увеличить планку прогресса на динамическое значение  
  
1. Установите <xref:System.Windows.Forms.ProgressBar> элемент <xref:System.Windows.Forms.ProgressBar.Minimum%2A> управления <xref:System.Windows.Forms.ProgressBar.Maximum%2A> и значения.  
  
2. Вызовите <xref:System.Windows.Forms.ProgressBar.Increment%2A> метод, чтобы изменить значение, отображаемые неопределивным вами.  
  
     Следующий пример кода иллюстрирует, как панель прогресса может вычислить, сколько дискового пространства было использовано во время операции копирования.  
  
     В следующем примере, когда каждый файл пишется на жесткий диск, панель прогресса и метка обновляются, чтобы отразить количество доступного пространства жесткого диска. Этот пример требует, чтобы <xref:System.Windows.Forms.Label> ваша <xref:System.Windows.Forms.ProgressBar> форма имеет элемент управления и элемента управления.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Общие сведения об элементе управления ProgressBar](progressbar-control-overview-windows-forms.md)
- [Элемент управления ProgressBar](progressbar-control-windows-forms.md)
