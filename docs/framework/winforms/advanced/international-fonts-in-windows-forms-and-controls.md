---
title: Международные шрифты в Windows Forms и элементах управления Windows
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 38a6928dfb548c6b514b598dbebe5bbc62d2e3f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="cb42c-102">Международные шрифты в Windows Forms и элементах управления Windows</span><span class="sxs-lookup"><span data-stu-id="cb42c-102">International Fonts in Windows Forms and Controls</span></span>
<span data-ttu-id="cb42c-103">В приложениях на разных языках выбора шрифтов рекомендуется использовать откат шрифта везде, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="cb42c-103">In International applications the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="cb42c-104">Это означает система определяет, что скрипт символ принадлежит.</span><span class="sxs-lookup"><span data-stu-id="cb42c-104">Font fallback means that the system determines what script the character belongs to.</span></span>  
  
## <a name="using-font-fallback"></a><span data-ttu-id="cb42c-105">Применение подмены шрифта</span><span class="sxs-lookup"><span data-stu-id="cb42c-105">Using Font Fallback</span></span>  
 <span data-ttu-id="cb42c-106">Чтобы воспользоваться этой функцией, не устанавливайте <xref:System.Drawing.Font> свойство формы или любого другого элемента.</span><span class="sxs-lookup"><span data-stu-id="cb42c-106">To take advantage of this feature, do not set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="cb42c-107">Приложение будет автоматически использовать системный шрифт по умолчанию, отличающийся от языка локализованной операционной системы в другую.</span><span class="sxs-lookup"><span data-stu-id="cb42c-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="cb42c-108">При запуске приложения, система автоматически выбирает правильный шрифт для языка и региональных параметров, выбранных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="cb42c-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>  
  
 <span data-ttu-id="cb42c-109">Существует исключение из правила не задавать шрифт, начертание шрифта изменением.</span><span class="sxs-lookup"><span data-stu-id="cb42c-109">There is an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="cb42c-110">Это может оказаться важным для приложения, в котором пользователь нажимает кнопку для отображения текста в текстовом поле был выделен полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="cb42c-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="cb42c-111">Чтобы сделать это, вы пишете функции для изменения стиля шрифта текстовое поле, будут выводиться полужирным шрифтом, зависимости от того, независимо от шрифта формы.</span><span class="sxs-lookup"><span data-stu-id="cb42c-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="cb42c-112">Очень важно, чтобы эта функция вызывается в двух местах: в кнопке <xref:System.Windows.Forms.Control.Click> обработчик событий и в <xref:System.Windows.Forms.Control.FontChanged> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="cb42c-112">It is important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="cb42c-113">Если функция вызывается только в <xref:System.Windows.Forms.Control.Click> обработчик событий и другие части кода изменяет семейства шрифтов для всей формы, текстовое поле не изменится с остальной частью формы.</span><span class="sxs-lookup"><span data-stu-id="cb42c-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box will not change with the rest of the form.</span></span>  
  
```  
' Visual Basic  
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
  
// C#  
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
  
 <span data-ttu-id="cb42c-114">Тем не менее при локализации приложения полужирный шрифт могут отображаться неправильно для определенных языков.</span><span class="sxs-lookup"><span data-stu-id="cb42c-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="cb42c-115">Если это критично, то локализаторам иметь возможность переключения шрифта с жирного шрифта на обычный текст.</span><span class="sxs-lookup"><span data-stu-id="cb42c-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="cb42c-116">Поскольку локализаторам обычно не являются разработчиками и не имеют доступа к исходному коду, только с файлами ресурсов, этот параметр необходимо задать в файлах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cb42c-116">Since localizers are typically not developers and do not have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="cb42c-117">Чтобы сделать это, необходимо установить <xref:System.Drawing.Font.Bold%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="cb42c-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="cb42c-118">Это приводит к записывается в файлы ресурсов, где локализаторам можно изменить начертание шрифта.</span><span class="sxs-lookup"><span data-stu-id="cb42c-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="cb42c-119">Затем написать код после `InitializeComponent` метод, который сбрасывает шрифт на основании шрифт независимо от формы, но использует начертание шрифта, указанное в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cb42c-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb42c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cb42c-120">See Also</span></span>  
 [<span data-ttu-id="cb42c-121">Глобализация Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb42c-121">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [<span data-ttu-id="cb42c-122">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="cb42c-122">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
