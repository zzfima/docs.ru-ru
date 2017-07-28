---
title: "Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip | Microsoft Docs"
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
  - "пользовательское рисование"
  - "рисование, пользовательский"
  - "рисование, владелец"
  - "примеры [Windows Forms], панели инструментов"
  - "рисование владельцем"
  - "ProfessionalColorTable - класс, переопределение"
  - "RenderMode - свойство"
  - "панели инструментов [Windows Forms], изменение цветов"
  - "панели инструментов [Windows Forms], пользовательское рисование"
  - "ToolStrip - элемент управления [Windows Forms], изменение цветов"
  - "ToolStrip - элемент управления [Windows Forms], рисование"
  - "ToolStripProfessionalRenderer - класс"
  - "ToolStripRenderer - класс"
  - "ToolStripRenderMode - класс"
  - "ToolStripSystemRenderer - класс"
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip
Элементы управления <xref:System.Windows.Forms.ToolStrip> имеют следующие связанные классы отрисовки:  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> предоставляет внешний вид и стиль операционной системы;  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> предоставляет внешний вид и стиль Microsoft Office;  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> является абстрактным базовым классом для двух других классов отрисовки.  
  
 Для настраиваемой отрисовки \(также известной как рисование владельцем\) элемента управления <xref:System.Windows.Forms.ToolStrip> можно переопределить один из классов отрисовки и изменить перспективу логики отрисовки.  
  
 В приведенных ниже процедурах описаны различные аспекты настраиваемой отрисовки.  
  
### Переключение между доступными средствами отрисовки  
  
-   Задайте для свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> требуемое значение <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
     Для <xref:System.Windows.Forms.ToolStripRenderMode> статический режим <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> определяет средство отрисовки для приложения.  Другие значения <xref:System.Windows.Forms.ToolStripRenderMode>: <xref:System.Windows.Forms.ToolStripRenderMode>, <xref:System.Windows.Forms.ToolStripRenderMode> и <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
### Изменение границ в стиле Microsoft Office на прямые  
  
-   Переопределите <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=fullName>, но не вызывайте базовый класс.  
  
> [!NOTE]
>  Существуют версии этого метода для <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
### Изменение ProfessionalColorTable  
  
-   Переопределите <xref:System.Windows.Forms.ProfessionalColorTable> и измените нужные цвета.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable   
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
  
    ```  
  
### Изменение отрисовки для всех элементов управления ToolStrip в приложении  
  
1.  С помощью свойства <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=fullName> выберите одно из доступных средств отрисовки.  
  
2.  Используйте <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> для назначения пользовательского средства отрисовки.  
  
3.  Убедитесь в том, что свойству <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName> присвоено значение по умолчанию <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
### Отключение цветов в стиле Microsoft Office для всего приложения  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=fullName> значение `false`.  
  
### Отключение цветов в стиле Microsoft Office для одного элемента управления ToolStrip  
  
-   Используйте код, аналогичный приведенному ниже.  
  
     \[Visual Basic\]  
  
    ```  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
  
    ```  
  
     \[C\#\]  
  
    ```  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 [Элементы управления Windows Forms со встроенной поддержки рисования владельцем](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)