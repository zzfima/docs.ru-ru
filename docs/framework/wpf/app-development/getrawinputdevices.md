---
title: Получение необработанных устройств ввода
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947918"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="0693e-102">Получение необработанных устройств ввода</span><span class="sxs-lookup"><span data-stu-id="0693e-102">GetRawInputDevices</span></span>
<span data-ttu-id="0693e-103">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="0693e-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0693e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0693e-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0693e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0693e-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="0693e-106">[out] Указатель на [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) для перечисления устройств необработанного ввода.</span><span class="sxs-lookup"><span data-stu-id="0693e-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0693e-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0693e-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="0693e-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="0693e-108">HRESULT:</span></span>  
  
 <span data-ttu-id="0693e-109">S_OK — [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) только будет использоваться программой PresentationHost.exe, если возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="0693e-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="0693e-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0693e-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0693e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0693e-111">Remarks</span></span>  
 <span data-ttu-id="0693e-112">Устройства необработанного ввода — это ряд устройств, включающий клавиатуры, мышь и менее распространенные устройства, такие как устройства удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="0693e-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="0693e-113">После получения списка устройств необработанного ввода программа PresentationHost.exe регистрируется в устройствах для получения уведомлений WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="0693e-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0693e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0693e-114">See also</span></span>

- [<span data-ttu-id="0693e-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="0693e-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="0693e-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="0693e-116">FilterInputMessage</span></span>](filterinputmessage.md)
