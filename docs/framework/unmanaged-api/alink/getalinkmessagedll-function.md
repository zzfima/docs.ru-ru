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
ms.openlocfilehash: 395dc85ad638e8a790962a4aa38019612c360ce1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="0a6b4-102">Функция GetALinkMessageDll</span><span class="sxs-lookup"><span data-stu-id="0a6b4-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="0a6b4-103">Находит и загружает библиотеку DLL сообщений.</span><span class="sxs-lookup"><span data-stu-id="0a6b4-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="0a6b4-104">Возвращает 0, если сообщение DLL невозможно найти или загрузить.</span><span class="sxs-lookup"><span data-stu-id="0a6b4-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="0a6b4-105">Сообщений DLL должна быть либо в подкаталоге, имя которого совпадает с Идентификатором языка, либо в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0a6b4-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a6b4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a6b4-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0a6b4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0a6b4-107">Requirements</span></span>  
 <span data-ttu-id="0a6b4-108">**Заголовок:** alink.h</span><span class="sxs-lookup"><span data-stu-id="0a6b4-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="0a6b4-109">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="0a6b4-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6b4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0a6b4-110">See Also</span></span>  
 [<span data-ttu-id="0a6b4-111">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="0a6b4-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
