---
title: Получение необработанных устройств ввода
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 4fc7a5021f9f8d9e6badcd3e13266fb8f4bfe7a4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991747"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="bece0-102">Получение необработанных устройств ввода</span><span class="sxs-lookup"><span data-stu-id="bece0-102">GetRawInputDevices</span></span>
<span data-ttu-id="bece0-103">Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="bece0-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bece0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bece0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bece0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bece0-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="bece0-106">заполняет Указатель на [иенумравинпутдевице](ienumrawinputdevice.md) для перечисления необработанных устройств ввода.</span><span class="sxs-lookup"><span data-stu-id="bece0-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bece0-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bece0-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="bece0-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="bece0-108">HRESULT:</span></span>  
  
 <span data-ttu-id="bece0-109">Значение S_OK- [иенумравинпутдевице](ienumrawinputdevice.md) будет использоваться в PresentationHost. exe только при возвращении S_OK.</span><span class="sxs-lookup"><span data-stu-id="bece0-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="bece0-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="bece0-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bece0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="bece0-111">Remarks</span></span>  
 <span data-ttu-id="bece0-112">Устройства необработанного ввода — это ряд устройств, включающий клавиатуры, мышь и менее распространенные устройства, такие как устройства удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="bece0-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="bece0-113">После получения списка устройств необработанного ввода программа PresentationHost.exe регистрируется в устройствах для получения уведомлений WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="bece0-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bece0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bece0-114">See also</span></span>

- [<span data-ttu-id="bece0-115">жетравинпутдевицелист</span><span class="sxs-lookup"><span data-stu-id="bece0-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="bece0-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="bece0-116">FilterInputMessage</span></span>](filterinputmessage.md)
