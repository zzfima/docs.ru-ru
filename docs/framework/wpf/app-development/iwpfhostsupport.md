---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964785"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="9d08f-102">Интерфейс IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="9d08f-102">IWpfHostSupport</span></span>
<span data-ttu-id="9d08f-103">Приложения, на [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] которых размещается содержимое с помощью PresentationHost. exe, реализуют этот интерфейс для обеспечения точки интеграции между узлом и PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="9d08f-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d08f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d08f-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="9d08f-105">такие приложения, как веб-браузеры, могут [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] размещать [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое, включая и свободный код XAML.</span><span class="sxs-lookup"><span data-stu-id="9d08f-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="9d08f-106">Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] содержимого приложения создают экземпляр [элемента управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="9d08f-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="9d08f-107">Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] служб создает экземпляр PresentationHost. exe, который предоставляет размещенное [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое на узле для показа в [элементе управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="9d08f-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="9d08f-108">Интеграция, включенная `IWpfHostSupport` в, позволяет PresentationHost. exe:</span><span class="sxs-lookup"><span data-stu-id="9d08f-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="9d08f-109">Обнаружение и регистрация с помощью необработанных устройств ввода (устройств с HID-интерфейсом), в которых заинтересован ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="9d08f-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="9d08f-110">Получение входных сообщений с зарегистрированных устройств ввода необработанных данных и пересылка соответствующих сообщений ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="9d08f-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="9d08f-111">Запросите ведущее приложение для пользовательского пользовательского интерфейса хода выполнения и ошибок.</span><span class="sxs-lookup"><span data-stu-id="9d08f-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d08f-112">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="9d08f-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="9d08f-113">Участники</span><span class="sxs-lookup"><span data-stu-id="9d08f-113">Members</span></span>  
  
|<span data-ttu-id="9d08f-114">Член</span><span class="sxs-lookup"><span data-stu-id="9d08f-114">Member</span></span>|<span data-ttu-id="9d08f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9d08f-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d08f-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="9d08f-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="9d08f-117">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="9d08f-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="9d08f-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="9d08f-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="9d08f-119">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9d08f-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="9d08f-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="9d08f-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="9d08f-121">По умолчанию PresentationHost. exe предоставляет собственный ход развертывания и пользовательские интерфейсы ошибок развертывания, отображаемые при развертывании содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="9d08f-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
