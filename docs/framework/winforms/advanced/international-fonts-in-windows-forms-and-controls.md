---
title: Международные шрифты в Windows Forms и элементы управления
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
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942900"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="3fe5d-102">Международные шрифты в Windows Forms и элементы управления</span><span class="sxs-lookup"><span data-stu-id="3fe5d-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="3fe5d-103">В приложения на разных языках выбора шрифтов рекомендуется использовать откат шрифта, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="3fe5d-104">Это означает что система определяет, что скрипт символ принадлежит.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="3fe5d-105">С помощью откат шрифта</span><span class="sxs-lookup"><span data-stu-id="3fe5d-105">Using font fallback</span></span>

<span data-ttu-id="3fe5d-106">Чтобы воспользоваться преимуществами этой функции, не устанавливайте <xref:System.Drawing.Font> свойство для форм или любого другого элемента.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="3fe5d-107">Приложение будет автоматически использовать системный шрифт по умолчанию, который отличается от языка локализованной операционной системы в другую.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="3fe5d-108">При запуске приложения, система автоматически выбирает правильный шрифт для языка и региональных параметров, выбранных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="3fe5d-109">Имеется исключение из правила шрифта, который предназначен для изменения стиля шрифта.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="3fe5d-110">Это может оказаться важным для приложения, в котором пользователь нажимает кнопку, чтобы текст в текстовом поле отображаются полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="3fe5d-111">Чтобы сделать это, следует написать функцию, чтобы изменить стиль шрифта текстового поля будут выводиться полужирным шрифтом, в зависимости от независимо от формы шрифта.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="3fe5d-112">Очень важно для вызова этой функции в двух местах: в кнопки <xref:System.Windows.Forms.Control.Click> обработчик событий и в <xref:System.Windows.Forms.Control.FontChanged> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="3fe5d-113">Если функция вызывается только в <xref:System.Windows.Forms.Control.Click> обработчик событий и некоторых других фрагмент кода изменяет семейство шрифтов для всей формы, текстовое поле не изменяется с остальной частью формы.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="3fe5d-114">Тем не менее при локализации приложения, полужирный шрифт может отображать плохо для определенных языков.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="3fe5d-115">Если это представляет собой проблему, вы локализаторам возможность переключения шрифта с жирного шрифта на обычный текст.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="3fe5d-116">Поскольку локализаторы обычно не являются разработчиками, а не имеют доступа к исходному коду, только с файлами ресурсов, этот параметр необходимо задать в файлах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="3fe5d-117">Чтобы сделать это, необходимо установить <xref:System.Drawing.Font.Bold%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="3fe5d-118">Результатом начертание шрифта, которая записывается в файлы ресурсов, где его можно изменить локализаторов.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="3fe5d-119">Затем написать код после `InitializeComponent` метод, который сбрасывает шрифт в зависимости от шрифта независимо от формы, но использует стиль шрифта, указанное в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3fe5d-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="3fe5d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3fe5d-120">See also</span></span>

- [<span data-ttu-id="3fe5d-121">Глобализация приложений Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3fe5d-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
- [<span data-ttu-id="3fe5d-122">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="3fe5d-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)
