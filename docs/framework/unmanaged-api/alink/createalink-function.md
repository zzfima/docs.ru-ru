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
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787621"
---
# <a name="createalink-function"></a><span data-ttu-id="2de92-102">Функция CreateALink</span><span class="sxs-lookup"><span data-stu-id="2de92-102">CreateALink Function</span></span>
<span data-ttu-id="2de92-103">Создает экземпляр компоновщика сборок и задает указатель на указанный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2de92-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2de92-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2de92-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2de92-105">Parameters</span></span>  
  
|<span data-ttu-id="2de92-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="2de92-106">Parameter</span></span>|<span data-ttu-id="2de92-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2de92-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="2de92-108">Физическое имя одного из интерфейсов компоновщика сборок.</span><span class="sxs-lookup"><span data-stu-id="2de92-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="2de92-109">Расположение, которое в случае успешного завершения содержит указатель на `riid` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2de92-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2de92-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2de92-110">Requirements</span></span>  
 <span data-ttu-id="2de92-111">**Библиотека**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="2de92-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de92-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2de92-112">See also</span></span>

- [<span data-ttu-id="2de92-113">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="2de92-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
