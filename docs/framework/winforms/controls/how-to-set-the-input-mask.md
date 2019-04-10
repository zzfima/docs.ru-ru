---
title: Практическое руководство. Определение маски ввода
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06eaf68fef167d63e6f8404dd5049f5445881d24
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331472"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="95dbb-102">Практическое руководство. Определение маски ввода</span><span class="sxs-lookup"><span data-stu-id="95dbb-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="95dbb-103">Элементе скрытого текстового поля является элементом поля расширенный текст, который поддерживает декларативный синтаксис для принятия или отклонения введенных пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="95dbb-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="95dbb-104">Установив свойство маски, можно указать допустимых входных данных без написания настраиваемую логику проверки в приложении.</span><span class="sxs-lookup"><span data-stu-id="95dbb-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="95dbb-105">Дополнительные сведения см. в разделе "Примечания" <xref:System.Windows.Forms.MaskedTextBox> класса.</span><span class="sxs-lookup"><span data-stu-id="95dbb-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="95dbb-106">Установка свойства маски вручную</span><span class="sxs-lookup"><span data-stu-id="95dbb-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="95dbb-107">Если вы знакомы с символами, которые поддерживает свойство маски, можно ввести вручную.</span><span class="sxs-lookup"><span data-stu-id="95dbb-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="95dbb-108">Сводка символы, которые поддерживает свойство маски, см. в разделе "Примечания" <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="95dbb-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="95dbb-109">Чтобы вручную задать свойство маски</span><span class="sxs-lookup"><span data-stu-id="95dbb-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="95dbb-110">В **разработки** представление, выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="95dbb-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="95dbb-111">В **свойства** окна, найдите <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="95dbb-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="95dbb-112">Введите значение маски.</span><span class="sxs-lookup"><span data-stu-id="95dbb-112">Type the mask that you want.</span></span> <span data-ttu-id="95dbb-113">Например, введите `###`.</span><span class="sxs-lookup"><span data-stu-id="95dbb-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="95dbb-114">С помощью диалогового окна маски ввода</span><span class="sxs-lookup"><span data-stu-id="95dbb-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="95dbb-115">В диалоговом окне маски ввода предоставляет несколько предопределенных масок ввода.</span><span class="sxs-lookup"><span data-stu-id="95dbb-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="95dbb-116">Можно также изменить предопределенные маски или ввести собственную маску вручную.</span><span class="sxs-lookup"><span data-stu-id="95dbb-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="95dbb-117">Чтобы открыть диалоговое окно маска ввода</span><span class="sxs-lookup"><span data-stu-id="95dbb-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="95dbb-118">В **разработки** представление, выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="95dbb-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="95dbb-119">Щелкните смарт-тег, чтобы открыть **задачи MaskedTextBox** панели.</span><span class="sxs-lookup"><span data-stu-id="95dbb-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="95dbb-120">Нажмите кнопку **определение маски**.</span><span class="sxs-lookup"><span data-stu-id="95dbb-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="95dbb-121">\- или -</span><span class="sxs-lookup"><span data-stu-id="95dbb-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="95dbb-122">В **свойства** выберите <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="95dbb-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="95dbb-123">Нажмите кнопку с многоточием в столбце значений свойств.</span><span class="sxs-lookup"><span data-stu-id="95dbb-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="95dbb-124">**Маска ввода** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="95dbb-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="95dbb-125">Чтобы использовать это диалоговое окно маска ввода</span><span class="sxs-lookup"><span data-stu-id="95dbb-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="95dbb-126">(Необязательно) Щелкните одну из стандартных масок в списке.</span><span class="sxs-lookup"><span data-stu-id="95dbb-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="95dbb-127">(Необязательно) Изменения в стандартные маски **маска** поле.</span><span class="sxs-lookup"><span data-stu-id="95dbb-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="95dbb-128">(Необязательно) Введите новую маску в **маска** поле.</span><span class="sxs-lookup"><span data-stu-id="95dbb-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="95dbb-129">То есть у вас использовать один из предопределенных масок.</span><span class="sxs-lookup"><span data-stu-id="95dbb-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95dbb-130">В окне предварительного просмотра отображаются символы, которые пользователь видит в <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="95dbb-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="95dbb-131">Эти символы имеются руководство, которое поможет пользователю ввести данные правильно.</span><span class="sxs-lookup"><span data-stu-id="95dbb-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="95dbb-132">Установите или снимите **использовать ValidatingType** "флажок".</span><span class="sxs-lookup"><span data-stu-id="95dbb-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="95dbb-133">**Использовать ValidatingType** флажок указывает, используется ли тип данных для проверки данных, вводимых пользователем.</span><span class="sxs-lookup"><span data-stu-id="95dbb-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="95dbb-134">Дополнительные сведения см. в описании свойства <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="95dbb-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="95dbb-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95dbb-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="95dbb-136">Маска вводится в **маска** свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="95dbb-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95dbb-137">См. также</span><span class="sxs-lookup"><span data-stu-id="95dbb-137">See also</span></span>

- [<span data-ttu-id="95dbb-138">Пошаговое руководство. Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="95dbb-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
