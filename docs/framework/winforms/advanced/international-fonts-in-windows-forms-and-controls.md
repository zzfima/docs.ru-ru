---
title: Международные шрифты в формах и элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743517"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="d4637-102">Международные шрифты в Windows Forms и элементы управления</span><span class="sxs-lookup"><span data-stu-id="d4637-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="d4637-103">В международных приложениях рекомендуемым методом выбора шрифтов является использование отката шрифта везде, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="d4637-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="d4637-104">Откат шрифта означает, что система определяет, к какому скрипту относится этот символ.</span><span class="sxs-lookup"><span data-stu-id="d4637-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="d4637-105">Использование отката шрифта</span><span class="sxs-lookup"><span data-stu-id="d4637-105">Using font fallback</span></span>

<span data-ttu-id="d4637-106">Чтобы воспользоваться этой функцией, не устанавливайте свойство <xref:System.Drawing.Font> для формы или любого другого элемента.</span><span class="sxs-lookup"><span data-stu-id="d4637-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="d4637-107">Приложение будет автоматически использовать системный шрифт по умолчанию, который отличается от локализованного языка операционной системы на другой.</span><span class="sxs-lookup"><span data-stu-id="d4637-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="d4637-108">При запуске приложения система автоматически предоставит правильный шрифт для языка и региональных параметров, выбранных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="d4637-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="d4637-109">Существует исключение в правиле «не задавать шрифт», которое предназначено для изменения стиля шрифта.</span><span class="sxs-lookup"><span data-stu-id="d4637-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="d4637-110">Это может быть важно для приложения, в котором пользователь нажимает кнопку, чтобы текст в текстовом поле отображался полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="d4637-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="d4637-111">Для этого необходимо написать функцию, чтобы изменить стиль шрифта текстового поля на полужирный, исходя из того, что имеет шрифт формы.</span><span class="sxs-lookup"><span data-stu-id="d4637-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="d4637-112">Важно вызывать эту функцию в двух местах: в обработчике событий <xref:System.Windows.Forms.Control.Click> кнопки и в обработчике событий <xref:System.Windows.Forms.Control.FontChanged>.</span><span class="sxs-lookup"><span data-stu-id="d4637-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="d4637-113">Если функция вызывается только в обработчике событий <xref:System.Windows.Forms.Control.Click>, а другой фрагмент кода изменяет семейство шрифтов всей формы, текстовое поле не изменяется в остальной части формы.</span><span class="sxs-lookup"><span data-stu-id="d4637-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="d4637-114">Однако при локализации приложения полужирный шрифт может плохо отображаться для определенных языков.</span><span class="sxs-lookup"><span data-stu-id="d4637-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="d4637-115">Если это важно, Локализаторы должны иметь возможность переключения шрифта с полужирного на обычный текст.</span><span class="sxs-lookup"><span data-stu-id="d4637-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="d4637-116">Так как локализаторы обычно не являются разработчиками и не имеют доступа к исходному коду только для файлов ресурсов, этот параметр необходимо задать в файлах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d4637-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="d4637-117">Для этого задайте для свойства <xref:System.Drawing.Font.Bold%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d4637-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="d4637-118">Это приводит к записанию параметра Font в файлы ресурсов, где локализаторы могут редактировать их.</span><span class="sxs-lookup"><span data-stu-id="d4637-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="d4637-119">Затем вы пишете код после метода `InitializeComponent` для сброса шрифта в зависимости от шрифта формы, но с использованием стиля шрифта, указанного в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d4637-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="d4637-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4637-120">See also</span></span>

- [<span data-ttu-id="d4637-121">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="d4637-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
