---
title: Начальная форма не указана
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 9af95b397bef4a19654510619cf0864c8ab7b76f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833572"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="2c42f-102">Начальная форма не указана</span><span class="sxs-lookup"><span data-stu-id="2c42f-102">A startup form has not been specified</span></span>
<span data-ttu-id="2c42f-103">Приложение использует <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса, но не указывает форму запуска.</span><span class="sxs-lookup"><span data-stu-id="2c42f-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="2c42f-104">Это может произойти, если **Включить исполняющую** флажок в конструкторе проектов, но **Начальная форма** не указан.</span><span class="sxs-lookup"><span data-stu-id="2c42f-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="2c42f-105">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c42f-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c42f-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2c42f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="2c42f-107">Укажите автоматически запускаемый объект для приложения.</span><span class="sxs-lookup"><span data-stu-id="2c42f-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="2c42f-108">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c42f-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="2c42f-109">Переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод, чтобы задать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойство форму запуска.</span><span class="sxs-lookup"><span data-stu-id="2c42f-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c42f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2c42f-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="2c42f-111">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c42f-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
