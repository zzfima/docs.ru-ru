---
title: "Практическое руководство: работа с элементами ActiveX (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Toolbox, adding controls
- ActiveX controls, adding to Toolbox
ms.assetid: ec675027-866f-4c05-aaf2-92fca5200f9a
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0ae1e5158ad83a6a7d45fa7820a707dbca1af3f3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-work-with-activex-controls-visual-basic"></a><span data-ttu-id="6a76e-102">Практическое руководство. Работа с элементами ActiveX (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a76e-102">How to: Work with ActiveX Controls (Visual Basic)</span></span>
<span data-ttu-id="6a76e-103">Элементы управления ActiveX являются компонентами COM или объекты, которые можно вставить в веб-страницу или другое приложение для использования упакованных функциональных возможностей, запрограммированных другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="6a76e-103">ActiveX controls are COM components or objects you can insert into a Web page or other application to reuse packaged functionality someone else has programmed.</span></span> <span data-ttu-id="6a76e-104">Элементы управления ActiveX, разработанные для Visual Basic 6.0 и более ранних версий можно использовать для добавления возможностей в **элементов** из [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a76e-104">You can use ActiveX controls developed for Visual Basic 6.0 and earlier versions to add features to the **Toolbox** of [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span></span>  
  
### <a name="to-add-activex-controls-to-the-toolbox"></a><span data-ttu-id="6a76e-105">Чтобы добавить элементы управления ActiveX на панель инструментов</span><span class="sxs-lookup"><span data-stu-id="6a76e-105">To add ActiveX controls to the toolbox</span></span>  
  
1.  <span data-ttu-id="6a76e-106">На **средства** меню, щелкните **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="6a76e-106">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="6a76e-107">**Выбор элементов панели элементов** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="6a76e-107">The **Choose Toolbox** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="6a76e-108">Щелкните **COM-компонентов** вкладки.</span><span class="sxs-lookup"><span data-stu-id="6a76e-108">Click the **COM Components** tab.</span></span>  
  
3.  <span data-ttu-id="6a76e-109">Установите флажок рядом с элементом управления ActiveX, вы хотите использовать и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6a76e-109">Select the check box next to the ActiveX control you want to use, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6a76e-110">Появится новый элемент управления с помощью средств в **элементов**.</span><span class="sxs-lookup"><span data-stu-id="6a76e-110">The new control appears with the other tools in the **Toolbox**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a76e-111">Программа Aximp вручную создать сборку взаимодействия для элементов управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="6a76e-111">You can use the Aximp utility to manually create an interop assembly for ActiveX controls.</span></span> <span data-ttu-id="6a76e-112">Дополнительные сведения см. в разделе [Aximp.exe (импортера элементов управления ActiveX Windows Forms)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0).</span><span class="sxs-lookup"><span data-stu-id="6a76e-112">For more information, see [Aximp.exe (Windows Forms ActiveX Control Importer)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a76e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6a76e-113">See Also</span></span>  
 <span data-ttu-id="6a76e-114">[Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="6a76e-114">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="6a76e-115"> [Практическое руководство: Добавление элементов управления ActiveX в Windows Forms](http://msdn.microsoft.com/library/54a61e5b-555e-4887-b41e-6244fed271eb) </span><span class="sxs-lookup"><span data-stu-id="6a76e-115"> [How to: Add ActiveX Controls to Windows Forms](http://msdn.microsoft.com/library/54a61e5b-555e-4887-b41e-6244fed271eb) </span></span>  
<span data-ttu-id="6a76e-116"> [AxImp.exe (программа импорта элементов управления ActiveX форм Windows)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0) </span><span class="sxs-lookup"><span data-stu-id="6a76e-116"> [Aximp.exe (Windows Forms ActiveX Control Importer)](http://msdn.microsoft.com/library/482c0d83-7144-4497-b626-87d2351b78d0) </span></span>  
<span data-ttu-id="6a76e-117"> [Вопросы размещения элемента управления ActiveX в Windows Forms](http://msdn.microsoft.com/library/2509302d-a74e-484f-9890-2acdbfa67a68) </span><span class="sxs-lookup"><span data-stu-id="6a76e-117"> [Considerations When Hosting an ActiveX Control on a Windows Form](http://msdn.microsoft.com/library/2509302d-a74e-484f-9890-2acdbfa67a68) </span></span>  
<span data-ttu-id="6a76e-118"> [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6a76e-118"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span></span>
