---
title: "Получение необработанных устройств ввода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e936b4ef2cab65e72ca9edbc3b95281815938983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getrawinputdevices"></a><span data-ttu-id="10351-102">Получение необработанных устройств ввода</span><span class="sxs-lookup"><span data-stu-id="10351-102">GetRawInputDevices</span></span>
<span data-ttu-id="10351-103">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="10351-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10351-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10351-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10351-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10351-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="10351-106">[out] Указатель на [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) для перечисления устройства необработанного ввода.</span><span class="sxs-lookup"><span data-stu-id="10351-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="10351-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10351-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="10351-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="10351-108">HRESULT:</span></span>  
  
 <span data-ttu-id="10351-109">Значение S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) будет использоваться только в PresentationHost.exe Если возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="10351-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="10351-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="10351-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10351-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="10351-111">Remarks</span></span>  
 <span data-ttu-id="10351-112">Устройства необработанного ввода — это ряд устройств, включающий клавиатуры, мышь и менее распространенные устройства, такие как устройства удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="10351-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="10351-113">После получения списка устройств необработанного ввода программа PresentationHost.exe регистрируется в устройствах для получения уведомлений WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="10351-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10351-114">См. также</span><span class="sxs-lookup"><span data-stu-id="10351-114">See Also</span></span>  
 [<span data-ttu-id="10351-115">http://MSDN.Microsoft.com/library/Default.ASP?URL=/Library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.ASP</span><span class="sxs-lookup"><span data-stu-id="10351-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="10351-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="10351-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
