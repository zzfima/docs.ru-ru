---
title: "Практическое руководство. Упорядочение дочерних форм интерфейса MDI | Microsoft Docs"
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
  - "дочерние формы, упорядочение"
  - "MDI - интерфейс, упорядочение дочерних форм"
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Упорядочение дочерних форм интерфейса MDI
Во многих случаях приложения будут иметь команды меню для таких действий как «Мозаика», «Каскад» и «Упорядочить», которые позволяют управлять компоновкой открытых дочерних MDI\-форм.  Для изменения порядка дочерних форм в родительской MDI\-форме можно использовать метод <xref:System.Windows.Forms.Form.LayoutMdi%2A> с одним из значений перечисления <xref:System.Windows.Forms.MdiLayout>.  
  
 Значения перечисления <xref:System.Windows.Forms.MdiLayout> позволяют отображать дочерние формы в виде каскада, мозаично по вертикали или горизонтали, либо в виде значков форм, расположенных в нижней части MDI\-формы.  Эти значения имеют тот же эффект, что и Windows\-команды **Окна каскадом**, **Отображать окна рядом**, **Отображать окна в виде стека** и **Показать рабочий стол**, соответственно.  
  
 Эти методы часто используются в качестве обработчиков событий, вызываемых с помощью события <xref:System.Windows.Forms.Control.Click> пункта меню.  Таким образом, пункт меню с текстом «Окна каскадом» может оказать требуемое воздействие на дочерние MDI\-окна.  
  
### Упорядочение дочерних форм  
  
1.  В методе для родительской MDI\-формы используйте перечисление <xref:System.Windows.Forms.Form.LayoutMdi%2A> для задания метода<xref:System.Windows.Forms.MdiLayout>.  В следующем примере используется значение перечисления <xref:System.Windows.Forms.MdiLayout?displayProperty=fullName> для дочерних окон родительской MDI\-формы \(`Form1`\).  Перечисление применяется в коде во время работы обработчика событий для события <xref:System.Windows.Forms.Control.Click> пункта меню **Окна каскадом**.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  Путем изменения значения перечисления <xref:System.Windows.Forms.MdiLayout> можно также мозаично размещать окна и упорядочивать их в виде значков.  
  
2.  В случае использования Visual C\# поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Практическое руководство. Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Практическое руководство. Отправка данных в активную дочернюю MDI\-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)