---
title: "Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28c90df258db8480f68eea05f922b36f30d81a3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="3aaae-102">Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3aaae-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="3aaae-103">Можно использовать в Windows Forms <xref:System.Windows.Forms.ErrorProvider> компонента для просмотра ошибок в столбцах набора данных или другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="3aaae-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="3aaae-104">Для <xref:System.Windows.Forms.ErrorProvider> компонент для отображения ошибок данных в форме, оно не обязательно должно непосредственно связаны с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3aaae-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="3aaae-105">После привязки к источнику данных, он может отображать значок ошибки рядом с любой элемент управления, который привязан к тому же источнику данных.</span><span class="sxs-lookup"><span data-stu-id="3aaae-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3aaae-106">Если изменить поставщик ошибок <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> и <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> свойства во время выполнения, следует использовать <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> метода во избежание конфликтов.</span><span class="sxs-lookup"><span data-stu-id="3aaae-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="3aaae-107">Для отображения ошибок данных</span><span class="sxs-lookup"><span data-stu-id="3aaae-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="3aaae-108">Привяжите этот компонент к определенному столбцу в таблице данных.</span><span class="sxs-lookup"><span data-stu-id="3aaae-108">Bind the component to a specific column within a data table.</span></span>  
  
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
  
2.  <span data-ttu-id="3aaae-109">Задать <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойства в форму.</span><span class="sxs-lookup"><span data-stu-id="3aaae-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="3aaae-110">Задайте положение текущей записи строку, содержащую ошибку столбца.</span><span class="sxs-lookup"><span data-stu-id="3aaae-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3aaae-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3aaae-111">See Also</span></span>  
 [<span data-ttu-id="3aaae-112">Общие сведения о компоненте ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="3aaae-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="3aaae-113">Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3aaae-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
