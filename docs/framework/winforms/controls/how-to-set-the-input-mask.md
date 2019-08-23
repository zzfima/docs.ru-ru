---
title: Практическое руководство. Определение маски ввода
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949146"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="29019-102">Практическое руководство. Определение маски ввода</span><span class="sxs-lookup"><span data-stu-id="29019-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="29019-103">Элемент управления "текстовое поле с маской" — Это Улучшенный элемент управления "текстовое поле", поддерживающий декларативный синтаксис для принятия или отклонения вводимых пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="29019-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="29019-104">Установив свойство Mask, можно указать допустимый пользовательский ввод без написания какой бы то ни было пользовательской логики проверки в приложении.</span><span class="sxs-lookup"><span data-stu-id="29019-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="29019-105">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.MaskedTextBox> "Примечания" класса.</span><span class="sxs-lookup"><span data-stu-id="29019-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="29019-106">Задание свойства маски вручную</span><span class="sxs-lookup"><span data-stu-id="29019-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="29019-107">Если вы знакомы с символами, которые поддерживает свойство Mask, можно ввести его вручную.</span><span class="sxs-lookup"><span data-stu-id="29019-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="29019-108">Общие сведения о символах, поддерживаемых свойством Mask, см. в разделе <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> "Примечания" Свойства.</span><span class="sxs-lookup"><span data-stu-id="29019-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="29019-109">Задание свойства маски вручную</span><span class="sxs-lookup"><span data-stu-id="29019-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="29019-110">В режиме **конструктора** выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="29019-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="29019-111">В <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> окне **Свойства** выберите свойство.</span><span class="sxs-lookup"><span data-stu-id="29019-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="29019-112">Введите нужную маску.</span><span class="sxs-lookup"><span data-stu-id="29019-112">Type the mask that you want.</span></span> <span data-ttu-id="29019-113">Например, введите `###`.</span><span class="sxs-lookup"><span data-stu-id="29019-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="29019-114">Использование диалогового окна «маска ввода»</span><span class="sxs-lookup"><span data-stu-id="29019-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="29019-115">Диалоговое окно «Маска ввода» предоставляет некоторые предопределенные маски ввода.</span><span class="sxs-lookup"><span data-stu-id="29019-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="29019-116">Можно также изменить стандартные маски или ввести собственную маску вручную.</span><span class="sxs-lookup"><span data-stu-id="29019-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="29019-117">Открытие диалогового окна «маска ввода»</span><span class="sxs-lookup"><span data-stu-id="29019-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="29019-118">В режиме **конструктора** выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="29019-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="29019-119">Щелкните смарт-тег, чтобы открыть панель **задачи MaskedTextBox** .</span><span class="sxs-lookup"><span data-stu-id="29019-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="29019-120">Щелкните **задать маску**.</span><span class="sxs-lookup"><span data-stu-id="29019-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="29019-121">\- или -</span><span class="sxs-lookup"><span data-stu-id="29019-121">\- or -</span></span>  
  
    1. <span data-ttu-id="29019-122">В окне **Свойства** выберите <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="29019-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="29019-123">Нажмите кнопку с многоточием в столбце значение свойства.</span><span class="sxs-lookup"><span data-stu-id="29019-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="29019-124">Откроется диалоговое окно **Маска ввода** .</span><span class="sxs-lookup"><span data-stu-id="29019-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="29019-125">Использование диалогового окна «маска ввода»</span><span class="sxs-lookup"><span data-stu-id="29019-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="29019-126">Используемых Выберите одну из стандартных масок в списке.</span><span class="sxs-lookup"><span data-stu-id="29019-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="29019-127">Используемых Измените стандартную маску в поле **Маска** .</span><span class="sxs-lookup"><span data-stu-id="29019-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="29019-128">Используемых Введите новую маску в поле **Маска** .</span><span class="sxs-lookup"><span data-stu-id="29019-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="29019-129">То есть вам не нужно использовать одну из стандартных масок.</span><span class="sxs-lookup"><span data-stu-id="29019-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="29019-130">В поле Предварительный просмотр отображаются символы, которые видит пользователь в <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="29019-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="29019-131">Эти символы являются руководством, помогающим пользователю правильно ввести данные.</span><span class="sxs-lookup"><span data-stu-id="29019-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="29019-132">Установите или снимите флажок **использовать валидатингтипе** .</span><span class="sxs-lookup"><span data-stu-id="29019-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="29019-133">Флажок **использовать валидатингтипе** указывает, используется ли тип данных для проверки данных, вводимых пользователем.</span><span class="sxs-lookup"><span data-stu-id="29019-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="29019-134">Дополнительные сведения см. в описании свойства <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="29019-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="29019-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="29019-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="29019-136">Маска указывается в свойстве **Mask** в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="29019-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29019-137">См. также</span><span class="sxs-lookup"><span data-stu-id="29019-137">See also</span></span>

- [<span data-ttu-id="29019-138">Пошаговое руководство: Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="29019-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
