---
title: "How to: Distinguish Between Clicks and Double-Clicks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "mouse, click"
  - "mouse, double-click"
  - "mouse clicks, single versus double"
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Distinguish Between Clicks and Double-Clicks
Как правило, одиночное событие *щелчок* инициирует действие пользовательского интерфейса, а событие *двойной щелчок* расширяет его.  Например, одним щелчком мыши обычно выбирается элемент, а двойным щелчком мыши этот элемент изменяется.  Однако события щелчков Windows Forms непросто приспособить к сценарию, в котором щелчок и двойной щелчок выполняют несовместимые действия, поскольку действие, привязанное к событию <xref:System.Windows.Forms.Control.Click> или <xref:System.Windows.Forms.Control.MouseClick>, выполняется перед действием, привязанным к событию <xref:System.Windows.Forms.Control.DoubleClick> или <xref:System.Windows.Forms.Control.MouseDoubleClick>.  В этом разделе показаны два способа решения этой проблемы.  Одним из решений является обработка события двойного щелчка и откат действий при обработке события щелчка.  В редких случаях может потребоваться имитировать поведение при одинарном и двойном щелчке при обработке событий <xref:System.Windows.Forms.Control.MouseDown> и с помощью свойств <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> и <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> класса <xref:System.Windows.Forms.SystemInformation>.  Производится измерение времени между щелчками мышью и, если второе нажатие происходит до того, как <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> достигнет значения и кнопка мыши была нажата, когда курсор находился в прямоугольнике, заданном <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, то выполняется действие двойного щелчка; в противном случае выполняется действие щелчка.  
  
### Выполнение отката щелчка кнопкой мыши  
  
-   Убедитесь, что элемент управления, с которым вы работаете, имеет стандартное поведение при двойном щелчке мышью.  В противном случае задействуйте элемент управления с помощью метода <xref:System.Windows.Forms.Control.SetStyle%2A>.  Обработайте событие двойного щелчка и откат к одиночному щелчку кнопкой мыши, а также действие двойного щелчка.  В следующем примере кода показано, как создать пользовательскую кнопку с включенным двойным щелчком мыши, а также как откатить к одиночному щелчку в коде обработки событий двойного щелчка.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### Различение щелчков в событии MouseDown  
  
-   Обработайте событие <xref:System.Windows.Forms.Control.MouseDown> и определите расположение и временной интервал между щелчками с помощью соответствующего свойства <xref:System.Windows.Forms.SystemInformation> и компонента <xref:System.Windows.Forms.Timer>.  Выполните необходимые действия в зависимости от того, имеет ли место щелчок или двойной щелчок кнопкой мыши.  В следующем примере кода показано, как это сделать.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## Компиляция кода  
 Для этих примеров требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этих примеров из командной строки для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)