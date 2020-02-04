---
title: Просмотр ошибок в наборе данных с помощью компонента ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745456"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms
Компонент <xref:System.Windows.Forms.ErrorProvider> Windows Forms можно использовать для просмотра ошибок столбцов в наборе данных или другом источнике. Чтобы компонент <xref:System.Windows.Forms.ErrorProvider> отображал ошибки данных в форме, ему не нужно напрямую связываться с элементом управления. После привязки к источнику данных он может отобразить значок ошибки рядом с любым элементом управления, привязанным к тому же источнику данных.  
  
> [!NOTE]
> При изменении свойств <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> и <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> поставщика ошибок во время выполнения следует использовать метод <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>, чтобы избежать конфликтов.  
  
### <a name="to-display-data-errors"></a>Отображение ошибок данных  
  
1. Привязка компонента к определенному столбцу в таблице данных.  
  
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
  
2. Задайте для свойства <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> форму.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. Установка в качестве расположения текущей записи строки, содержащей ошибку столбца.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о компоненте ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
