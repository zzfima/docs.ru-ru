---
title: "Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged | Microsoft Docs"
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
  - "BindingSource - компонент [Windows Forms], и IPropertyChange"
  - "BindingSource - компонент [Windows Forms], примеры"
  - "уведомления об изменениях"
  - "уведомления об изменениях, возникновение"
  - "источники данных, обнаружение изменений"
  - "примеры [Windows Forms], BindingSource - компонент"
  - "INotifyPropertyChanged - интерфейс, использование с BindingSource"
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged
Компонент <xref:System.Windows.Forms.BindingSource> автоматически обнаруживает изменения в источнике данных, когда тип, содержащийся в этом источнике, реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и вызывает события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> при изменении значения свойства.  Это очень удобно, так как элементы управления, привязанные к <xref:System.Windows.Forms.BindingSource>, будут автоматически обновляться при изменении значений источника данных.  
  
> [!NOTE]
>  Если источник данных реализует <xref:System.ComponentModel.INotifyPropertyChanged> и выполняются асинхронные операции, не следует вносить изменения в источник данных в фоновом потоке.  Вместо этого рекомендуется считывать данные в фоновом потоке и объединять их в список в потоке пользовательского интерфейса.  
  
## Пример  
 В следующем примере кода показан пример простой реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>.  Также показано, как компонент <xref:System.Windows.Forms.BindingSource> автоматически передает изменения источника данных в связанный элемент управления, когда <xref:System.Windows.Forms.BindingSource> привязан к списку типа <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 При использовании атрибута `CallerMemberName` в вызовах метода `NotifyPropertyChanged` нет необходимости указывать имя свойства в качестве строкового аргумента.  Дополнительные сведения см. в разделе [Сведения о вызывающем](../Topic/Caller%20Information%20\(C%23%20and%20Visual%20Basic\).md).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.ComponentModel.INotifyPropertyChanged>   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Практическое руководство. Уведомление об изменении данных с использованием метода ResetItem компонента BindingSource](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)