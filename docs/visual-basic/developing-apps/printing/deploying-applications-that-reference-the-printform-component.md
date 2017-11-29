---
title: "Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15b6e21e769c90e23e66e4f87b37f74462423985
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="0f847-102">Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f847-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="0f847-103">Если требуется развернуть приложение, которое ссылается на компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , этот компонент должен быть установлен на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f847-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="0f847-104">Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="0f847-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="0f847-105">Установка PrintForm в качестве необходимого компонента</span><span class="sxs-lookup"><span data-stu-id="0f847-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="0f847-106">Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="0f847-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="0f847-107">Процесс установки необходимых компонентов называется *начальной загрузкой*.</span><span class="sxs-lookup"><span data-stu-id="0f847-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="0f847-108">Когда компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> установлен на компьютере разработчика, пакет начального загрузчика Microsoft Visual Basic Power Packs добавляется в каталог начального загрузчика [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f847-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="0f847-109">Этот пакет доступен при добавлении необходимых компонентов для [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] или для развертывания установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="0f847-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="0f847-110">По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки.</span><span class="sxs-lookup"><span data-stu-id="0f847-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="0f847-111">Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0f847-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f847-112">Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f847-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="0f847-113">Для приложений [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения независимо от уровня безопасности, заданного приложением.</span><span class="sxs-lookup"><span data-stu-id="0f847-113">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="0f847-114">После установки приложения пользователь может запустить приложение без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="0f847-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="0f847-115">Во время установки пользователям будет предложено установить компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , если он отсутствует на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f847-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="0f847-116">В качестве альтернативы начальному загрузчику можно предварительно развернуть компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> с помощью электронной системы распространения ПО, например Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="0f847-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f847-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0f847-117">See also</span></span>  
 [<span data-ttu-id="0f847-118">Практическое руководство. Установка необходимых компонентов для приложения ClickOnce</span><span class="sxs-lookup"><span data-stu-id="0f847-118">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="0f847-119">Компонент PrintForm</span><span class="sxs-lookup"><span data-stu-id="0f847-119">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
