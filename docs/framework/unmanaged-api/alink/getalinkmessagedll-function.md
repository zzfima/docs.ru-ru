---
title: Функция GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449342"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="d8ee3-102">Функция GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="d8ee3-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="d8ee3-103">Находит и загружает библиотеку DLL сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8ee3-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="d8ee3-104">Возвращает 0, если не удалось обнаружить или загрузить библиотеку DLL сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8ee3-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="d8ee3-105">DLL сообщения должна быть либо в подкаталоге, имя которого является ИДЕНТИФИКАТОРом языка, либо в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d8ee3-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ee3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8ee3-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d8ee3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d8ee3-107">Requirements</span></span>  
 <span data-ttu-id="d8ee3-108">**Заголовок:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="d8ee3-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="d8ee3-109">**Библиотека**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="d8ee3-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ee3-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8ee3-110">See also</span></span>

- [<span data-ttu-id="d8ee3-111">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="d8ee3-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
