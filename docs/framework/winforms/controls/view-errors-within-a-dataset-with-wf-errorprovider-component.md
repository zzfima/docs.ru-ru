---
title: Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: f00d874f2a4afcea3498a64fe946a93c83eb7b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537090"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms
Можно использовать в Windows Forms <xref:System.Windows.Forms.ErrorProvider> компонента для просмотра ошибок в столбцах набора данных или другого источника данных. Для <xref:System.Windows.Forms.ErrorProvider> компонент для отображения ошибок данных в форме, оно не обязательно должно непосредственно связаны с элементом управления. После привязки к источнику данных, он может отображать значок ошибки рядом с любой элемент управления, который привязан к тому же источнику данных.  
  
> [!NOTE]
>  Если изменить поставщик ошибок <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> и <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> свойства во время выполнения, следует использовать <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> метода во избежание конфликтов.  
  
### <a name="to-display-data-errors"></a>Для отображения ошибок данных  
  
1.  Привяжите этот компонент к определенному столбцу в таблице данных.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  Задать <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойства в форму.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  Задайте положение текущей записи строку, содержащую ошибку столбца.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о компоненте ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
