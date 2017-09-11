---
title: "Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b625e0c58653f1ee9a2d263d7d2d29ad3b2e3c1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="1c77b-102">Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c77b-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="1c77b-103">Если требуется развернуть приложение, которое ссылается на <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента, компонент должен устанавливаться на конечном компьютере.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="1c77b-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="1c77b-104">Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="1c77b-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="1c77b-105">Установка в качестве необходимого компонента PrintForm</span><span class="sxs-lookup"><span data-stu-id="1c77b-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="1c77b-106">Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="1c77b-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="1c77b-107">Процесс установки необходимых компонентов называется *начальной загрузкой*.</span><span class="sxs-lookup"><span data-stu-id="1c77b-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="1c77b-108">Когда <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонент установлен на компьютере разработчика, пакет начального загрузчика Microsoft Visual Basic Power Packs добавляется [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] каталог загрузчика.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="1c77b-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="1c77b-109">Этот пакет доступен, то при выполнении процедуры для добавления необходимых для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] или развертывания установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="1c77b-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="1c77b-110">По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки.</span><span class="sxs-lookup"><span data-stu-id="1c77b-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="1c77b-111">Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="1c77b-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c77b-112">Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c77b-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="1c77b-113">Для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] приложений, это означает, что пользователю могут потребоваться права администратора для установки приложения, независимо от уровня безопасности, заданного приложением.</span><span class="sxs-lookup"><span data-stu-id="1c77b-113">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="1c77b-114">После установки приложения пользователь может запустить приложение без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="1c77b-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="1c77b-115">Во время установки, пользователям будет предложено установить <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента, если он отсутствует на конечном компьютере.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="1c77b-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="1c77b-116">В качестве альтернативы начальному загрузчику можно предварительно развернуть <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента с помощью электронной системы распространения как Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="1c77b-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c77b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1c77b-117">See also</span></span>  
 <span data-ttu-id="1c77b-118">[Практическое руководство: Установка необходимых компонентов с помощью приложения ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="1c77b-118">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="1c77b-119"> [Компонент PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)</span><span class="sxs-lookup"><span data-stu-id="1c77b-119"> [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)</span></span>
