---
title: Получение необработанных устройств ввода
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 18564e0de8f88e89f8fb71d28ee3bfeccceea4ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507568"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="8b0bc-102">Получение необработанных устройств ввода</span><span class="sxs-lookup"><span data-stu-id="8b0bc-102">GetRawInputDevices</span></span>
<span data-ttu-id="8b0bc-103">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="8b0bc-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b0bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b0bc-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b0bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b0bc-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="8b0bc-106">[out] Указатель на [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) для перечисления устройств необработанного ввода.</span><span class="sxs-lookup"><span data-stu-id="8b0bc-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8b0bc-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b0bc-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="8b0bc-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="8b0bc-108">HRESULT:</span></span>  
  
 <span data-ttu-id="8b0bc-109">S_OK — [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) только будет использоваться программой PresentationHost.exe, если возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="8b0bc-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="8b0bc-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8b0bc-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b0bc-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b0bc-111">Remarks</span></span>  
 <span data-ttu-id="8b0bc-112">Устройства необработанного ввода — это ряд устройств, включающий клавиатуры, мышь и менее распространенные устройства, такие как устройства удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="8b0bc-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="8b0bc-113">После получения списка устройств необработанного ввода программа PresentationHost.exe регистрируется в устройствах для получения уведомлений WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="8b0bc-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b0bc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8b0bc-114">See also</span></span>
- [<span data-ttu-id="8b0bc-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="8b0bc-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="8b0bc-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="8b0bc-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
