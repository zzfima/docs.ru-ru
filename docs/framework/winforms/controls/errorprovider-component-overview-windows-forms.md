---
title: "Общие сведения о компоненте ErrorProvider (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ErrorProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "сообщения об ошибках, отображение"
  - "ErrorProvider - компонент [Windows Forms], сведения о компоненте ErrorProvider"
  - "ошибки [Windows Forms], отображение для пользователей"
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о компоненте ErrorProvider (Windows Forms)
Компонент форм Windows [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) предназначен для проверки данных, введенных пользователем в форму или элемент управления.  Обычно он используется вместе с проверкой сведений, вводимых в форму пользователем, или отображением ошибок в наборе данных.  Использование поставщика ошибок — лучший вариант выбора по сравнению с отображением сообщения об ошибке в соответствующем окне, поскольку после закрытия этого окна сообщение об ошибке более не отображается.  Компонент <xref:System.Windows.Forms.ErrorProvider> отображает значок ошибки \(![Значок ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.png "vbErrorProviderIcon")\) рядом с соответствующим элементом управления, например текстовым полем; при установке курсора мыши на значке ошибки появляется ToolTip, отображающий строку сообщения об ошибке.  
  
## Ключевые свойства  
 Основные свойства компонента <xref:System.Windows.Forms.ErrorProvider>: <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> и <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.  Если используется компонент <xref:System.Windows.Forms.ErrorProvider> с элементами управления с привязкой к данным, то для отображения компонентом значка ошибки в форме должен быть задан соответствующий контейнер \(обычно форма Windows\) для свойства <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>.  Если этот компонент добавляется в конструкторе, для свойства <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> устанавливается включающая его форма; если этот элемент управления добавляется в коде, необходимо установить его самостоятельно.  
  
 Для свойства <xref:System.Windows.Forms.ErrorProvider.Icon%2A> вместо устанавливаемого по умолчанию значка ошибки имеется возможность задать пользовательский значок.  Если задано свойство <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, компонент <xref:System.Windows.Forms.ErrorProvider> может отображать сообщения об ошибках для набора данных.  Основной метод компонента <xref:System.Windows.Forms.ErrorProvider.SetError%2A> — метод <xref:System.Windows.Forms.ErrorProvider>, указывающий строку сообщения об ошибке и место нахождения значка ошибки.  
  
> [!NOTE]
>  Компонент <xref:System.Windows.Forms.ErrorProvider> не имеет встроенной поддержки клиентских приложений со специальными возможностями.  Чтобы приложение было доступно при использовании этого компонента, необходимо реализовать дополнительный механизм обратной связи со специальными возможностями.  
  
## См. также  
 <xref:System.Windows.Forms.ErrorProvider>   
 [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)   
 [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)