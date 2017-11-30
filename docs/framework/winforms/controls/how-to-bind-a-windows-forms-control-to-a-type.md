---
title: "Практическое руководство. Связывание элемента управления с типом в Windows Forms"
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
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffde36d9644dade3372292a6fb3961cbbfb6a5da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Практическое руководство. Связывание элемента управления с типом в Windows Forms
При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту. Такая ситуация особенно часто возникает на этапе разработки, когда данные недоступны, но все равно нужно, чтобы элемент управления отображал данные из открытого интерфейса типа. Например, вы привязываете элемент управления <xref:System.Windows.Forms.DataGridView> к объекту, предоставляемому веб-службой, и хотите, чтобы во время разработки элемент управления <xref:System.Windows.Forms.DataGridView> помечал свои столбцы именами членов пользовательского типа.  
  
 Элемент управления можно легко привязать к типу с помощью компонента <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как привязать элемент управления <xref:System.Windows.Forms.DataGridView> к пользовательскому типу с помощью компонента <xref:System.Windows.Forms.BindingSource>. После запуска примера можно увидеть, что <xref:System.Windows.Forms.DataGridView> пометил столбцы, отражающие свойства объекта `Customer`, перед заполнением элемента управления данными. В примере есть кнопка Add Customer (Добавить клиента) для добавления данных в элемент управления <xref:System.Windows.Forms.DataGridView>. При нажатии на кнопку новый объект `Customer` добавляется в <xref:System.Windows.Forms.BindingSource>. В реальном сценарии данные можно было бы получить путем вызова веб-службы или другого источника данных.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
