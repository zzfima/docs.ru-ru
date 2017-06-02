---
title: "Практическое руководство. Связывание с веб-службой с помощью компонента BindingSource в Windows Forms | Microsoft Docs"
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
  - "BindingSource - компонент [Windows Forms], привязка к веб-службе"
  - "BindingSource - компонент [Windows Forms], примеры"
  - "элементы управления [Windows Forms], привязка к веб-службе"
  - "примеры [Windows Forms], BindingSource - компонент"
  - "веб-службы, привязка элементов управления"
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Практическое руководство. Связывание с веб-службой с помощью компонента BindingSource в Windows Forms
Компонент <xref:System.Windows.Forms.BindingSource> можно использовать, если необходимо привязать элемент управления Windows Form к результатам вызова веб\-служб XML.   Эта процедура аналогична привязке компонента <xref:System.Windows.Forms.BindingSource> к типу.  Необходимо создать клиентский прокси, который содержит методы и типы, предоставляемые веб\-службой.  Клиентский прокси веб\-службы можно создать либо непосредственно в самой веб\-службе \(ASMX\-файл\) или с помощью файла языка описания веб\-служб \(WSDL\-файл\).  Кроме того, клиентский прокси должен предоставлять доступ к полям сложных типов, используемых веб\-службой, в виде общих свойств.  Затем <xref:System.Windows.Forms.BindingSource> привязывается к одному из типов, доступных в прокси веб\-службы.  
  
### Создание и привязка к прокси на стороне клиента  
  
1.  Создайте форму Windows Forms в каталоге по своему усмотрению с подходящим пространством имен.  
  
2.  Добавьте в форму компонент <xref:System.Windows.Forms.BindingSource>.  
  
3.  Откройте командную строку [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] и перейдите к каталогу, в котором расположена форма.  
  
4.  С помощью средства WSDL введите `wsdl` и URL\-адрес для ASMX\- или WSDL\-файла веб\-службы, пространство имен приложения и при необходимости язык, с которым вы работаете.  
  
     В следующем примере кода используется веб\-служба, расположенная по адресу http:\/\/webservices.eraserver.  net\/zipcoderesolver\/zipcoderesolver.asmx.  Например, для C\# введите `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, для Visual Basic введите `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.  Передача пути в качестве аргумента для средства WSDL создаст клиентский прокси в том же каталоге и с тем пространством имен, что и у  приложения, и на указанном языке.  Если вы используете [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], добавьте файл в проект.  
  
5.  Выберите тип для привязки в клиентском прокси.  
  
     Обычно это тип, возвращаемый методом, предлагаемым веб\-службой.  Поля выбранного типа должны предоставляться как общие свойства для привязки.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  Задайте для свойства <xref:System.Windows.Forms.BindingSource.DataSource%2A> в <xref:System.Windows.Forms.BindingSource> нужный тип, содержащийся в клиентском прокси веб\-службы.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### Привязка элементов управления к компоненту BindingSource, который привязан к веб\-службе  
  
-   Привяжите элементы управления к <xref:System.Windows.Forms.BindingSource>, передав в качестве параметра общее свойство типа веб\-службы.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## Пример  
 В следующем примере кода показано, как привязать компонент <xref:System.Windows.Forms.BindingSource> к веб\-службе, а затем привязать текстовое поле к компоненту <xref:System.Windows.Forms.BindingSource>.  При нажатии кнопки вызывается метод веб\-службы, результаты будут отображаться в `textbox1`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## Компиляция кода  
 Это завершенный пример, включающий метод `Main` и сокращенную версию кода клиентского прокси.  
  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing, System.Web.Services, System.Windows.Forms и System.XML.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)