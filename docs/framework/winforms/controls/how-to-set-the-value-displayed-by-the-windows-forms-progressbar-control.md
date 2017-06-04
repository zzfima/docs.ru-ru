---
title: "Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Increment - метод"
  - "PerformStep - метод"
  - "элементы управления хода выполнения, установка отображаемого значения"
  - "ProgressBar - элемент управления [Windows Forms], установка отображаемого значения"
  - "Step - свойство"
  - "Value - свойство"
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Установка значения, отображаемого c помощью элемента управления ProgressBar в Windows Forms
> [!IMPORTANT]
>  Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] позволяет отображать заданное заданное значение в элементе управления <xref:System.Windows.Forms.ProgressBar> несколькими способами.  Выбор способа зависит от поставленной задачи или проблемы, которую требуется решить.  В следующей таблице показаны доступные для выбора подходы.  
  
|Подход|Описание|  
|------------|--------------|  
|Задайте значение элемента управления <xref:System.Windows.Forms.ProgressBar> напрямую.|Этот подход используется в задачах, когда известно точное количество используемых элементов, например при чтении записей из источника данных.  Помимо этого, данный подход можно использовать и в том случае, если нужно задать значение один или два раза.  Наконец, данный подход можно использовать, если требуется уменьшить значение, отображаемое индикатором выполнения.|  
|Увеличьте отображаемое значение элемента управления <xref:System.Windows.Forms.ProgressBar> на фиксированную величину.|Этот способ можно использовать при отображении простого счета между минимумом и максимумом, например при отображении затраченного времени или количества файлов из известного общего количества, которые были обработаны.|  
|Увеличьте отображаемое значение элемента управления <xref:System.Windows.Forms.ProgressBar> на переменную величину.|Этот способ можно использовать, когда требуется изменить отображаемое значение несколько раз на различные величины.  В качестве примера выбрано количество места на жестком диске, которое расходуется при записи набора файлов на диск.|  
  
 Самый прямой способ задать значение, отображаемое индикатором выполнения, — задать значение свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>.  Это можно сделать в режиме разработки, а также во время выполнения.  
  
### Чтобы задать значение элемента управления ProgressBar напрямую  
  
1.  Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.  
  
2.  В коде задайте для свойства <xref:System.Windows.Forms.ProgressBar.Value%2A> элемента управления целочисленное значение, которое находится между указанными минимумом и максимумом.  
  
    > [!NOTE]
    >  Если задать значение свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>, которое выходит за рамки диапазона, установленного свойствами <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>, элемент управления создает исключение <xref:System.ArgumentException>.  
  
     В следующем примере кода показано, как задать значение элемента управления <xref:System.Windows.Forms.ProgressBar> напрямую.  С помощью кода считываются записи из источника данных. Каждый раз при считывании записи обновляются индикатор выполнения и его метка.  Для данного примера требуется присутствие на форме элемента управления <xref:System.Windows.Forms.Label>, элемента управления <xref:System.Windows.Forms.ProgressBar> и таблицы данных со строкой`CustomerRow` c полями`FirstName` и`Last Name` .  
  
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
  
     При отображении хода выполнения, который увеличивается на постоянный числовой интервал, можно задать значение и затем вызвать метод, который увеличивает значение элемента управления <xref:System.Windows.Forms.ProgressBar> на этот числовой интервал.  Это используется в таймерах и других сценариях, когда ход выполнения не измеряется в процентах от общей величины.  
  
### Чтобы увеличить отображаемое значение индикатора выполнения на фиксированную величину  
  
1.  Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.  
  
2.  В качестве значения свойства <xref:System.Windows.Forms.ProgressBar.Step%2A> задайте целое число, представляющее величину, на которую следует увеличить отображаемое значение индикатора выполнения.  
  
3.  Вызовите метод <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> для изменения отображаемого значения на величину, заданную в свойстве <xref:System.Windows.Forms.ProgressBar.Step%2A>.  
  
     В следующем примере кода показано, как с помощью индикатора выполнения обеспечить подсчет файлов в ходе операции копирования.  
  
     В следующем примере индикатор выполнения и надпись обновляются по мере считывания каждого файла в память, чтобы отображать общее количество считанных файлов.  В этом примере требуется, чтобы форма содержала элемент управления <xref:System.Windows.Forms.Label> и элемент управления <xref:System.Windows.Forms.ProgressBar>.  
  
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
  
     Наконец, можно увеличить значение, отображаемое индикатором выполнения, таким образом, чтобы каждое приращение являлось уникальным числом.  Это используется при отслеживании серий уникальных операций, например при записи файлов различных размеров на жесткий диск или при измерении хода выполнения в процентах от общего значения.  
  
### Чтобы увеличить отображаемое значение индикатора выполнения на переменную величину  
  
1.  Задайте значения <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> элемента управления <xref:System.Windows.Forms.ProgressBar>.  
  
2.  Вызовите метод <xref:System.Windows.Forms.ProgressBar.Increment%2A> для изменения отображаемого значения на указанную величину.  
  
     В следующем примере кода показано, как с помощью индикатора выполнения можно рассчитать объем пространства на жестком диске, использованного в ходе операции копирования.  
  
     В следующем примере индикатор выполнения и надпись обновляются по мере записи каждого файла на жесткий диск, чтобы отражать количество свободного места на жестком диске.  В этом примере требуется, чтобы форма содержала элемент управления <xref:System.Windows.Forms.Label> и элемент управления <xref:System.Windows.Forms.ProgressBar>.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.ProgressBar>   
 <xref:System.Windows.Forms.ToolStripProgressBar>   
 [Общие сведения об элементе управления ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-overview-windows-forms.md)   
 [Элемент управления ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)