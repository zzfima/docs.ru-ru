---
title: "Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
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
ms.openlocfilehash: ad1aba4f2e725abbe560f0c71fbb543e15741200
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="7e162-102">Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="7e162-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="7e162-103">Если вы хотите развернуть приложение, которое ссылается на элементы управления пакетов Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), элементов управления необходимо установить на конечный компьютер.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape></span><span class="sxs-lookup"><span data-stu-id="7e162-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="7e162-104">Установка элементов управления пакетов Power Packs как необходимый компонент</span><span class="sxs-lookup"><span data-stu-id="7e162-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="7e162-105">Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="7e162-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="7e162-106">Процесс установки необходимых компонентов называется *начальной загрузкой*.</span><span class="sxs-lookup"><span data-stu-id="7e162-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="7e162-107">Когда [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] установлен на компьютере разработчика, добавляется пакет загрузчика Power Packs [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] каталог загрузчика.</span><span class="sxs-lookup"><span data-stu-id="7e162-107">When [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="7e162-108">Этот пакет доступен, то при выполнении процедуры для добавления необходимых для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] или развертывания установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="7e162-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="7e162-109">По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки.</span><span class="sxs-lookup"><span data-stu-id="7e162-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="7e162-110">Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="7e162-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e162-111">Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e162-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="7e162-112">Для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] приложений, это означает, что пользователю могут потребоваться права администратора для установки приложения, независимо от уровня безопасности, заданного приложением.</span><span class="sxs-lookup"><span data-stu-id="7e162-112">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="7e162-113">После установки приложения пользователь может запустить приложение без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="7e162-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="7e162-114">Во время установки пользователям будет предложено установить элементы управления пакетов Power Packs, если они не существуют на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e162-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="7e162-115">В качестве альтернативы начальному загрузчику можно предварительно развернуть элементы управления пакетов Power Packs с помощью электронной системы распространения как Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="7e162-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e162-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7e162-116">See also</span></span>  
 <span data-ttu-id="7e162-117">[Практическое руководство: Установка необходимых компонентов с помощью приложения ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="7e162-117">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="7e162-118"> [Элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span><span class="sxs-lookup"><span data-stu-id="7e162-118"> [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span></span>
