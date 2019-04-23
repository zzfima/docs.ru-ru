---
title: Практическое руководство. Создать только для чтения текстовое поле (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 72dc188993474ad4b39f0cfa74cadffdb99ff46f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308579"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="c044b-102">Практическое руководство. Создать только для чтения текстовое поле (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c044b-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="c044b-103">Изменяемое поле текста в Windows Forms можно преобразовать в элемент управления только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c044b-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="c044b-104">Например текстовое поле может отобразить значение обычно изменяется, но в настоящее время не может быть из-за состояния приложения.</span><span class="sxs-lookup"><span data-stu-id="c044b-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="c044b-105">Чтобы создать поле только для чтения текста</span><span class="sxs-lookup"><span data-stu-id="c044b-105">To create a read-only text box</span></span>  
  
1. <span data-ttu-id="c044b-106">Задайте <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="c044b-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="c044b-107">Со свойством, имеющим значение `true`, пользователи могут прокручивать и выделите текст в текстовом поле, не позволяя изменять.</span><span class="sxs-lookup"><span data-stu-id="c044b-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="c044b-108">Объект **копирования** команда работает в текстовом поле, но **Вырезать** и **вставить** команд не.</span><span class="sxs-lookup"><span data-stu-id="c044b-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c044b-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Свойство оказывает влияние на взаимодействие с пользователем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c044b-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="c044b-110">По-прежнему изменением содержимого текстового поля программными средствами во время выполнения, изменив <xref:System.Windows.Forms.TextBox.Text%2A> свойства текстового поля.</span><span class="sxs-lookup"><span data-stu-id="c044b-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c044b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c044b-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="c044b-112">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="c044b-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="c044b-113">Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="c044b-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="c044b-114">Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c044b-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c044b-115">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="c044b-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="c044b-116">Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="c044b-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c044b-117">Практическое руководство. Просмотр нескольких строк в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="c044b-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c044b-118">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="c044b-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
