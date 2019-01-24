---
title: Начальная форма не указана
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: f05358f76829768d8ff5c4ac85b5134f35254126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627217"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="869f6-102">Начальная форма не указана</span><span class="sxs-lookup"><span data-stu-id="869f6-102">A startup form has not been specified</span></span>
<span data-ttu-id="869f6-103">Приложение использует <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса, но не указывает форму запуска.</span><span class="sxs-lookup"><span data-stu-id="869f6-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="869f6-104">Это может произойти, если **Включить исполняющую** флажок в конструкторе проектов, но **Начальная форма** не указан.</span><span class="sxs-lookup"><span data-stu-id="869f6-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="869f6-105">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="869f6-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="869f6-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="869f6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="869f6-107">Укажите автоматически запускаемый объект для приложения.</span><span class="sxs-lookup"><span data-stu-id="869f6-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="869f6-108">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="869f6-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="869f6-109">Переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод, чтобы задать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойство форму запуска.</span><span class="sxs-lookup"><span data-stu-id="869f6-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869f6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="869f6-110">See also</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="869f6-111">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="869f6-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
