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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41e79a4c9587e3e738039cbf6a84087a2e7fc9b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741955"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="64b0d-102">Функция GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="64b0d-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="64b0d-103">Находит и загружает сообщения библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="64b0d-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="64b0d-104">Возвращает 0, если Библиотека сообщений не может быть расположен или загружен.</span><span class="sxs-lookup"><span data-stu-id="64b0d-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="64b0d-105">Сообщение DLL должно быть либо в подкаталоге, имя которого совпадает с Идентификатором языка, либо в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="64b0d-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64b0d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64b0d-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="64b0d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="64b0d-107">Requirements</span></span>  
 <span data-ttu-id="64b0d-108">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="64b0d-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="64b0d-109">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="64b0d-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b0d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="64b0d-110">See also</span></span>

- [<span data-ttu-id="64b0d-111">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="64b0d-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
