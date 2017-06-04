---
title: "Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "привязка данных, DataGridView - элемент управления"
  - "привязка данных, сетки"
  - "DataGridView - элемент управления [Windows Forms], привязка данных"
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную модель привязки данных Windows Forms, допускающую привязку к разнообразным источникам данных.  Однако в большинстве случаев выполняется привязка к компоненту <xref:System.Windows.Forms.BindingSource>, который управляет деталями взаимодействия с источником данных.  Компонент <xref:System.Windows.Forms.BindingSource> может представлять любой источник данных Windows Forms и обеспечивает большую гибкость при выборе или изменении расположения данных.  Подробнее об источниках данных, поддерживаемых элементом управления <xref:System.Windows.Forms.DataGridView>, см. в разделе [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
 В Visual Studio предусмотрена расширенная поддержка данной задачи.  См. также [Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).  
  
## Процедура  
  
#### Подключение элемента управления DataGridView к данным  
  
1.  Реализуйте метод, обрабатывающий получение данных из базы данных.  В примере кода ниже реализован метод `GetData`, инициализирующий компонент <xref:System.Data.SqlClient.SqlDataAdapter> и использующий его для заполнения <xref:System.Data.DataTable>.  <xref:System.Data.DataTable> затем привязывается к компоненту <xref:System.Windows.Forms.BindingSource>.  Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.  Вам потребуется доступ к серверу с примером базы данных SQL Server под именем Northwind.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  В обработчике событий <xref:System.Windows.Forms.Form.Load> формы привяжите элемент управления <xref:System.Windows.Forms.DataGridView> к компоненту <xref:System.Windows.Forms.BindingSource> и вызовите метод `GetData` для извлечения данных из базы данных.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## Пример  
 В примере полного кода ниже содержатся кнопки для повторной загрузки данных из базы данных и отправки в нее изменений.  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Windows.Forms, System.Data и System.XML.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Безопасность платформы .NET Framework  
 Хранение конфиденциальных сведений \(например, пароля\) в строке подключения может повлиять на безопасность приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Подробнее см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)