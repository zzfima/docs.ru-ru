---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423653"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="a49cd-102">Интерфейс IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="a49cd-102">IWpfHostSupport</span></span>
<span data-ttu-id="a49cd-103">Приложения, которые размещают [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимое через PresentationHost. exe, реализуют этот интерфейс для обеспечения точки интеграции между узлом и PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="a49cd-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a49cd-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="a49cd-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] <span data-ttu-id="a49cd-105">приложения, такие как веб-браузеры, могут размещать содержимое WPF, включая приложения браузера XAML (XBAP) и свободный XAML.</span><span class="sxs-lookup"><span data-stu-id="a49cd-105">applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="a49cd-106">Для размещения содержимого WPF [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложения создают экземпляр [элемента управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="a49cd-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="a49cd-107">Для размещения WPF создает экземпляр PresentationHost. exe, который обеспечивает размещение содержимого WPF на узле для показа в [элементе управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="a49cd-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="a49cd-108">Интеграция, включенная `IWpfHostSupport`, позволяет PresentationHost. exe:</span><span class="sxs-lookup"><span data-stu-id="a49cd-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="a49cd-109">Обнаружение и регистрация с помощью необработанных устройств ввода (устройств с HID-интерфейсом), в которых заинтересован ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="a49cd-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="a49cd-110">Получение входных сообщений с зарегистрированных устройств ввода необработанных данных и пересылка соответствующих сообщений ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="a49cd-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="a49cd-111">Запросите ведущее приложение для пользовательского пользовательского интерфейса хода выполнения и ошибок.</span><span class="sxs-lookup"><span data-stu-id="a49cd-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a49cd-112">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="a49cd-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="a49cd-113">Члены</span><span class="sxs-lookup"><span data-stu-id="a49cd-113">Members</span></span>  
  
|<span data-ttu-id="a49cd-114">Член</span><span class="sxs-lookup"><span data-stu-id="a49cd-114">Member</span></span>|<span data-ttu-id="a49cd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a49cd-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a49cd-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="a49cd-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="a49cd-117">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="a49cd-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="a49cd-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="a49cd-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="a49cd-119">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a49cd-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="a49cd-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="a49cd-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="a49cd-121">По умолчанию PresentationHost. exe предоставляет собственный ход развертывания и пользовательские интерфейсы ошибок развертывания, отображаемые при развертывании содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="a49cd-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
