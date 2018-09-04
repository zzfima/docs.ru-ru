---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 57d9ef87a078655a89a5869a48a1bd16f21b000f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500930"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="b6762-102">Интерфейс IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b6762-102">IWpfHostSupport</span></span>
<span data-ttu-id="b6762-103">Приложения, размещающие [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимым при помощи PresentationHost.exe Реализуйте этот интерфейс для предоставления точки интеграции между узлом и PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b6762-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6762-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6762-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="b6762-105"> можно размещать приложения, такие как веб-браузеры [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимого, включая [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и Свободный XAML.</span><span class="sxs-lookup"><span data-stu-id="b6762-105"> applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="b6762-106">Узел [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложения создают экземпляр [элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="b6762-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="b6762-107">Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] создает экземпляр класса PresentationHost.exe, который предоставляет размещаемый [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимого на узле для отображения в [элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="b6762-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="b6762-108">Интеграция включаемые `IWpfHostSupport` позволяет PresentationHost.exe для:</span><span class="sxs-lookup"><span data-stu-id="b6762-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
-   <span data-ttu-id="b6762-109">Определить и зарегистрировать устройства необработанного ввода (HID-устройств), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="b6762-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
-   <span data-ttu-id="b6762-110">Получите входящие сообщения от зарегистрированного устройства необработанного ввода и переслать соответствующие сообщения ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="b6762-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
-   <span data-ttu-id="b6762-111">Запрос ведущим приложением для настраиваемых пользовательских интерфейсов хода выполнения и ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6762-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6762-112">Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере</span><span class="sxs-lookup"><span data-stu-id="b6762-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="b6762-113">Члены</span><span class="sxs-lookup"><span data-stu-id="b6762-113">Members</span></span>  
  
|<span data-ttu-id="b6762-114">Член</span><span class="sxs-lookup"><span data-stu-id="b6762-114">Member</span></span>|<span data-ttu-id="b6762-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b6762-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6762-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="b6762-116">GetRawInputDevices</span></span>](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|<span data-ttu-id="b6762-117">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="b6762-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="b6762-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="b6762-118">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|<span data-ttu-id="b6762-119">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b6762-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="b6762-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b6762-120">GetCustomUI</span></span>](../../../../docs/framework/wpf/app-development/getcustomui.md)|<span data-ttu-id="b6762-121">По умолчанию PresentationHost.exe время от времени предоставляет свой собственный ход выполнения развертывания и ошибка развертывания при пользовательские интерфейсы, которые отображаются при развертывании содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="b6762-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
