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
ms.openlocfilehash: 993848711f41c9e03b969a3c611982a5c8bc860d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742219"
---
# <a name="createalink-function"></a><span data-ttu-id="99900-102">Функция CreateALink</span><span class="sxs-lookup"><span data-stu-id="99900-102">CreateALink Function</span></span>
<span data-ttu-id="99900-103">Создает экземпляр компоновщика сборок и задает указатель на указанный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="99900-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99900-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99900-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99900-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99900-105">Parameters</span></span>  
  
|<span data-ttu-id="99900-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="99900-106">Parameter</span></span>|<span data-ttu-id="99900-107">Описание</span><span class="sxs-lookup"><span data-stu-id="99900-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="99900-108">Физическое имя одного из интерфейсов компоновщика сборок.</span><span class="sxs-lookup"><span data-stu-id="99900-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="99900-109">Расположение, которое при успешном завершении содержит указатель на `riid` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="99900-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99900-110">Требования</span><span class="sxs-lookup"><span data-stu-id="99900-110">Requirements</span></span>  
 <span data-ttu-id="99900-111">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="99900-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99900-112">См. также</span><span class="sxs-lookup"><span data-stu-id="99900-112">See also</span></span>

- [<span data-ttu-id="99900-113">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="99900-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
