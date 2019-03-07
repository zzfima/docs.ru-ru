---
title: Функция CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11117db08d58684cc854400424d1836ec35b8c12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498016"
---
# <a name="createalink-function"></a><span data-ttu-id="06c0f-102">Функция CreateALink</span><span class="sxs-lookup"><span data-stu-id="06c0f-102">CreateALink Function</span></span>
<span data-ttu-id="06c0f-103">Создает экземпляр компоновщика сборок и задает указатель на указанный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="06c0f-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06c0f-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c0f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06c0f-105">Parameters</span></span>  
  
|<span data-ttu-id="06c0f-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="06c0f-106">Parameter</span></span>|<span data-ttu-id="06c0f-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="06c0f-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="06c0f-108">Физическое имя одного из интерфейсов компоновщика сборок.</span><span class="sxs-lookup"><span data-stu-id="06c0f-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="06c0f-109">Расположение, которое при успешном завершении содержит указатель на `riid` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="06c0f-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06c0f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="06c0f-110">Requirements</span></span>  
 <span data-ttu-id="06c0f-111">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="06c0f-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c0f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="06c0f-112">See also</span></span>
- [<span data-ttu-id="06c0f-113">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="06c0f-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
