---
title: "Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными | Microsoft Docs"
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
  - "BindingSource - компонент [Windows Forms], обработка ошибок и исключений"
  - "привязка данных, обработка ошибок"
  - "привязка данных, примеры"
  - "обработка ошибок, привязка данных"
  - "обработка ошибок, примеры"
  - "примеры [Windows Forms], обработка ошибок"
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными
Зачастую при привязке базовых бизнес\-объектов к элементам управления возникают ошибки и исключения.  Эти ошибки и исключения можно перехватывать, а затем исправлять или передавать сведения об ошибке пользователю путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete> для конкретного компонента <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> или <xref:System.Windows.Forms.CurrencyManager>.  
  
## Пример  
 В данном примере кода показан способ обработки ошибок и исключений, возникающих при выполнении операции привязки данных.  Он демонстрирует перехват ошибок путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName> объектов <xref:System.Windows.Forms.Binding>.  Для перехвата ошибок и исключений с помощью обработки этого события необходимо включить поддержку форматирования для привязки.  Форматирование можно включить при создании привязки или добавлении в коллекцию привязок, или установив значение свойства <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> равным `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Во время выполнения, если введена пустая строка в качестве имени или значение меньше 100 в качестве числа, то появится окно с сообщением.  Это происходит в результате обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName> для привязок этих текстовых полей.  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=fullName>   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)