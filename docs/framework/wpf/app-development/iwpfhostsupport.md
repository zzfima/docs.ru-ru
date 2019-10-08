---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 85309e46403b2f22f9afb760d4c4ae370c39246b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004088"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="2266e-102">Интерфейс IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="2266e-102">IWpfHostSupport</span></span>
<span data-ttu-id="2266e-103">Приложения, которые размещают [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимого с помощью PresentationHost. exe, реализуют этот интерфейс для обеспечения точки интеграции между узлом и PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="2266e-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2266e-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2266e-104">Remarks</span></span>  
 <span data-ttu-id="2266e-105">приложения [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], такие как веб-браузеры, могут размещать содержимое WPF, в том числе [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободный XAML.</span><span class="sxs-lookup"><span data-stu-id="2266e-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="2266e-106">Для размещения содержимого WPF приложения [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] создают экземпляр [элемента управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="2266e-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="2266e-107">Для размещения WPF создает экземпляр PresentationHost. exe, который обеспечивает размещение содержимого WPF на узле для показа в [элементе управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="2266e-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="2266e-108">Интеграция, включенная `IWpfHostSupport`, позволяет PresentationHost. exe выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2266e-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="2266e-109">Обнаружение и регистрация с помощью необработанных устройств ввода (устройств с HID-интерфейсом), в которых заинтересован ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="2266e-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="2266e-110">Получение входных сообщений с зарегистрированных устройств ввода необработанных данных и пересылка соответствующих сообщений ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="2266e-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="2266e-111">Запросите ведущее приложение для пользовательского пользовательского интерфейса хода выполнения и ошибок.</span><span class="sxs-lookup"><span data-stu-id="2266e-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2266e-112">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="2266e-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="2266e-113">Участники</span><span class="sxs-lookup"><span data-stu-id="2266e-113">Members</span></span>  
  
|<span data-ttu-id="2266e-114">Член</span><span class="sxs-lookup"><span data-stu-id="2266e-114">Member</span></span>|<span data-ttu-id="2266e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2266e-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2266e-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="2266e-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="2266e-117">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="2266e-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="2266e-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="2266e-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="2266e-119">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2266e-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="2266e-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="2266e-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="2266e-121">По умолчанию PresentationHost. exe предоставляет собственный ход развертывания и пользовательские интерфейсы ошибок развертывания, отображаемые при развертывании содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="2266e-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
