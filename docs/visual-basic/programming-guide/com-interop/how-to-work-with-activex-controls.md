---
title: "Практическое руководство. Работа с элементами ActiveX (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Toolbox, adding controls
- ActiveX controls, adding to Toolbox
ms.assetid: ec675027-866f-4c05-aaf2-92fca5200f9a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7856149d22f8949d8acbbd405649a12ad2f8113
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-work-with-activex-controls-visual-basic"></a><span data-ttu-id="23be3-102">Практическое руководство. Работа с элементами ActiveX (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23be3-102">How to: Work with ActiveX Controls (Visual Basic)</span></span>
<span data-ttu-id="23be3-103">Элементы управления ActiveX являются компоненты COM или объекты, которые можно вставить в веб-страницы или другое приложение для использования упакованных функциональных возможностей, запрограммированных другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="23be3-103">ActiveX controls are COM components or objects you can insert into a Web page or other application to reuse packaged functionality someone else has programmed.</span></span> <span data-ttu-id="23be3-104">Элементы управления ActiveX, разработанные для Visual Basic 6.0 и более ранних версиях можно использовать для добавления возможностей в **элементов** из [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23be3-104">You can use ActiveX controls developed for Visual Basic 6.0 and earlier versions to add features to the **Toolbox** of [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-add-activex-controls-to-the-toolbox"></a><span data-ttu-id="23be3-105">Чтобы добавить элементы управления ActiveX на панель элементов</span><span class="sxs-lookup"><span data-stu-id="23be3-105">To add ActiveX controls to the toolbox</span></span>  
  
1.  <span data-ttu-id="23be3-106">На **средства** меню, нажмите кнопку **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="23be3-106">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="23be3-107">**Выбор элементов панели элементов** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="23be3-107">The **Choose Toolbox** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="23be3-108">Нажмите кнопку **COM-компонентов** вкладки.</span><span class="sxs-lookup"><span data-stu-id="23be3-108">Click the **COM Components** tab.</span></span>  
  
3.  <span data-ttu-id="23be3-109">Установите флажок рядом с элементом управления ActiveX, которые вы хотите использовать и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23be3-109">Select the check box next to the ActiveX control you want to use, and then click **OK**.</span></span>  
  
     <span data-ttu-id="23be3-110">Новый элемент управления отображается с другими инструментами в **элементов**.</span><span class="sxs-lookup"><span data-stu-id="23be3-110">The new control appears with the other tools in the **Toolbox**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23be3-111">Программа Aximp для создания сборки взаимодействия для элементов управления ActiveX вручную.</span><span class="sxs-lookup"><span data-stu-id="23be3-111">You can use the Aximp utility to manually create an interop assembly for ActiveX controls.</span></span> <span data-ttu-id="23be3-112">Дополнительные сведения см. в разделе [Aximp.exe (импортера элементов управления ActiveX Windows Forms)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0).</span><span class="sxs-lookup"><span data-stu-id="23be3-112">For more information, see [Aximp.exe (Windows Forms ActiveX Control Importer)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23be3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="23be3-113">See Also</span></span>  
 [<span data-ttu-id="23be3-114">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="23be3-114">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="23be3-115">Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23be3-115">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="23be3-116">Aximp.exe (программа импорта элементов ActiveX форм Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="23be3-116">Aximp.exe (Windows Forms ActiveX Control Importer)</span></span>](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0)  
 [<span data-ttu-id="23be3-117">Вопросы размещения элемента управления ActiveX в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23be3-117">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>](../../../framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)  
 [<span data-ttu-id="23be3-118">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="23be3-118">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
