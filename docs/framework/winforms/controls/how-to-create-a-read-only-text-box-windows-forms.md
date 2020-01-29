---
title: Практическое руководство. Создание текстового поля только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731273"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="a6109-102">Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a6109-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="a6109-103">Можно преобразовать редактируемое Windows Forms текстовое поле в элемент управления только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a6109-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="a6109-104">Например, текстовое поле может отображать значение, которое обычно редактируется, но может не быть в данный момент из-за состояния приложения.</span><span class="sxs-lookup"><span data-stu-id="a6109-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="a6109-105">Создание текстового поля, доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6109-105">To create a read-only text box</span></span>

1. <span data-ttu-id="a6109-106">Задайте для свойства <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> элемента управления <xref:System.Windows.Forms.TextBox> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a6109-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="a6109-107">Если свойство имеет значение `true`, пользователи по-прежнему могут прокручивать и выделять текст в текстовом поле, не разрешая изменения.</span><span class="sxs-lookup"><span data-stu-id="a6109-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="a6109-108">Команда **копирования** работает в текстовом поле, но команды **вырезания** и **вставки** не используются.</span><span class="sxs-lookup"><span data-stu-id="a6109-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6109-109">Свойство <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> влияет только на взаимодействие с пользователем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6109-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="a6109-110">Вы по-прежнему можете изменить содержимое текстового поля программно во время выполнения, изменив свойство <xref:System.Windows.Forms.TextBox.Text%2A> текстового поля.</span><span class="sxs-lookup"><span data-stu-id="a6109-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6109-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6109-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a6109-112">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a6109-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a6109-113">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6109-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="a6109-114">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6109-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a6109-115">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="a6109-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a6109-116">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6109-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a6109-117">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6109-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a6109-118">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a6109-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
