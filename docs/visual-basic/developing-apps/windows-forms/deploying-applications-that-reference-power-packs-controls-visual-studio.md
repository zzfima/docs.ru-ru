---
title: Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a9562acf05cd27eed7bc1ad963845af9a7ca5f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="bea38-102">Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="bea38-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="bea38-103">Если вы хотите развернуть приложение, которое ссылается на элементы управления пакетов Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), элементы управления необходимо установить на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bea38-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="bea38-104">Установка элементов управления пакетов Power Packs как необходимый компонент</span><span class="sxs-lookup"><span data-stu-id="bea38-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="bea38-105">Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="bea38-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="bea38-106">Процесс установки необходимых компонентов называется *начальной загрузкой*.</span><span class="sxs-lookup"><span data-stu-id="bea38-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="bea38-107">Когда [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] установлен на компьютере разработчика Power Packs, пакет начального загрузчика добавляется [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] каталог начального загрузчика.</span><span class="sxs-lookup"><span data-stu-id="bea38-107">When [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="bea38-108">Этот пакет доступен при добавлении необходимых компонентов для [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] или для развертывания установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="bea38-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="bea38-109">По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки.</span><span class="sxs-lookup"><span data-stu-id="bea38-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="bea38-110">Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="bea38-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bea38-111">Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bea38-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="bea38-112">Для приложений [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения независимо от уровня безопасности, заданного приложением.</span><span class="sxs-lookup"><span data-stu-id="bea38-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="bea38-113">После установки приложения пользователь может запустить приложение без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="bea38-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="bea38-114">Во время установки пользователям будет предложено установить элементы управления пакетов Power Packs, если они не присутствуют на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bea38-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="bea38-115">В качестве альтернативы начальному загрузчику можно предварительно развернуть элементы управления пакетов Power Packs с помощью электронной системы распространения по как Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="bea38-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea38-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bea38-116">See also</span></span>  
 [<span data-ttu-id="bea38-117">Практическое руководство. Установка необходимых компонентов для приложения ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bea38-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="bea38-118">Элементы управления Visual Basic Power Packs</span><span class="sxs-lookup"><span data-stu-id="bea38-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
