---
title: Начальная форма не указана
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 301f249e6222c929d2c513964ecbb21df5fbc47f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976192"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="6f84b-102">Начальная форма не указана</span><span class="sxs-lookup"><span data-stu-id="6f84b-102">A startup form has not been specified</span></span>

<span data-ttu-id="6f84b-103">Приложение использует класс <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>, но не задает начальную форму.</span><span class="sxs-lookup"><span data-stu-id="6f84b-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="6f84b-104">Это может произойти, если в конструкторе проектов установлен флажок **Включить платформу приложений** , но не указана **Форма запуска** .</span><span class="sxs-lookup"><span data-stu-id="6f84b-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="6f84b-105">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6f84b-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f84b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f84b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="6f84b-107">Укажите объект запуска для приложения.</span><span class="sxs-lookup"><span data-stu-id="6f84b-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="6f84b-108">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6f84b-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="6f84b-109">Переопределите метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>, чтобы задать для свойства <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> начальную форму.</span><span class="sxs-lookup"><span data-stu-id="6f84b-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f84b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6f84b-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="6f84b-111">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6f84b-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
