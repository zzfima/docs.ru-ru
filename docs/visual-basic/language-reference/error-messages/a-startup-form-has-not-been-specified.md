---
title: "Начальная форма не указана"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdffc182ee66497d68aafb7dc37cfef75b4d2e9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="76d9b-102">Начальная форма не указана</span><span class="sxs-lookup"><span data-stu-id="76d9b-102">A startup form has not been specified</span></span>
<span data-ttu-id="76d9b-103">Приложение использует <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса, но не указывает начальную форму.</span><span class="sxs-lookup"><span data-stu-id="76d9b-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="76d9b-104">Это может произойти, если **Включить исполняющую среду** флажок в конструкторе проектов, но **Начальная форма** не указан.</span><span class="sxs-lookup"><span data-stu-id="76d9b-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="76d9b-105">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="76d9b-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76d9b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="76d9b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="76d9b-107">Укажите автоматически запускаемый объект для приложения.</span><span class="sxs-lookup"><span data-stu-id="76d9b-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="76d9b-108">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="76d9b-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="76d9b-109">Переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод, чтобы задать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойства форму запуска.</span><span class="sxs-lookup"><span data-stu-id="76d9b-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d9b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="76d9b-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="76d9b-111">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76d9b-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
