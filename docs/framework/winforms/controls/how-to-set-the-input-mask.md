---
title: "Практическое руководство. Определение маски ввода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.MaskPropertyEditor
helpviewer_keywords: MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c136bd5bdacec04a011f728694550fb66ae6d897
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="f54a6-102">Практическое руководство. Определение маски ввода</span><span class="sxs-lookup"><span data-stu-id="f54a6-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="f54a6-103">Элементе скрытого текстового поля является элементом поля расширенного текста, который поддерживает декларативный синтаксис для принятия или отклонения введенных пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="f54a6-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="f54a6-104">Установив свойство маски, можно указать допустимых входных данных без написания настраиваемую логику проверки в приложении.</span><span class="sxs-lookup"><span data-stu-id="f54a6-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="f54a6-105">Дополнительные сведения см. в разделе «Примечания» <xref:System.Windows.Forms.MaskedTextBox> класса.</span><span class="sxs-lookup"><span data-stu-id="f54a6-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="f54a6-106">Установка свойства маски вручную</span><span class="sxs-lookup"><span data-stu-id="f54a6-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="f54a6-107">Если вы знакомы с символами, которые поддерживает свойство маски, можно ввести вручную.</span><span class="sxs-lookup"><span data-stu-id="f54a6-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="f54a6-108">Сводка символов, которые поддерживает свойство маски, в разделе «Примечания» <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f54a6-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="f54a6-109">Чтобы задать свойство маски вручную</span><span class="sxs-lookup"><span data-stu-id="f54a6-109">To set the Mask property manually</span></span>  
  
1.  <span data-ttu-id="f54a6-110">В **разработки** представление, выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f54a6-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2.  <span data-ttu-id="f54a6-111">В **свойства** окна, найдите <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f54a6-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3.  <span data-ttu-id="f54a6-112">Введите маску, которая требуется.</span><span class="sxs-lookup"><span data-stu-id="f54a6-112">Type the mask that you want.</span></span> <span data-ttu-id="f54a6-113">Например, введите `###`.</span><span class="sxs-lookup"><span data-stu-id="f54a6-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="f54a6-114">С помощью диалогового окна маски ввода</span><span class="sxs-lookup"><span data-stu-id="f54a6-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="f54a6-115">Диалоговое окно маски ввода предоставляет несколько предопределенных масок ввода.</span><span class="sxs-lookup"><span data-stu-id="f54a6-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="f54a6-116">Можно также изменить предопределенные маски или ввести собственную маску вручную.</span><span class="sxs-lookup"><span data-stu-id="f54a6-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="f54a6-117">Чтобы открыть диалоговое окно маска ввода</span><span class="sxs-lookup"><span data-stu-id="f54a6-117">To open the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="f54a6-118">В **разработки** представление, выберите <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f54a6-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="f54a6-119">Щелкните смарт-тег, чтобы открыть **задачи MaskedTextBox** панель.</span><span class="sxs-lookup"><span data-stu-id="f54a6-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="f54a6-120">Нажмите кнопку **Установка маски**.</span><span class="sxs-lookup"><span data-stu-id="f54a6-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="f54a6-121">\- или -</span><span class="sxs-lookup"><span data-stu-id="f54a6-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="f54a6-122">В **свойства** выберите <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f54a6-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="f54a6-123">Нажмите кнопку с многоточием в столбце значений свойств.</span><span class="sxs-lookup"><span data-stu-id="f54a6-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="f54a6-124">**Маска ввода** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f54a6-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="f54a6-125">Чтобы воспользоваться диалоговым окном маска ввода</span><span class="sxs-lookup"><span data-stu-id="f54a6-125">To use the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="f54a6-126">(Необязательно) Щелкните одну из стандартных масок в списке.</span><span class="sxs-lookup"><span data-stu-id="f54a6-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2.  <span data-ttu-id="f54a6-127">(Необязательно) Изменения в стандартные маски **маска** поле.</span><span class="sxs-lookup"><span data-stu-id="f54a6-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3.  <span data-ttu-id="f54a6-128">(Необязательно) Введите новую маску в **маска** поле.</span><span class="sxs-lookup"><span data-stu-id="f54a6-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="f54a6-129">То есть используйте одну из стандартных масок нет.</span><span class="sxs-lookup"><span data-stu-id="f54a6-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f54a6-130">В окне предварительного просмотра отобразится символы, которые пользователь видит в <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f54a6-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="f54a6-131">Эти символы имеются помогает пользователю правильно ввести данные.</span><span class="sxs-lookup"><span data-stu-id="f54a6-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4.  <span data-ttu-id="f54a6-132">Установите или снимите **использовать ValidatingType** флажок.</span><span class="sxs-lookup"><span data-stu-id="f54a6-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="f54a6-133">**Использовать ValidatingType** флажок указывает, используется ли тип данных для проверки данных, введенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="f54a6-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="f54a6-134">Дополнительные сведения см. в описании свойства <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54a6-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5.  <span data-ttu-id="f54a6-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f54a6-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="f54a6-136">Маска вводится в **маска** свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="f54a6-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54a6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f54a6-137">See Also</span></span>  
 [<span data-ttu-id="f54a6-138">Пример. Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="f54a6-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
