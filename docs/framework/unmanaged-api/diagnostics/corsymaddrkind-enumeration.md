---
title: Перечисление CorSymAddrKind
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133527"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="3b802-102">Перечисление CorSymAddrKind</span><span class="sxs-lookup"><span data-stu-id="3b802-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="3b802-103">Указывает тип адреса памяти.</span><span class="sxs-lookup"><span data-stu-id="3b802-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b802-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b802-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="3b802-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3b802-105">Members</span></span>  
  
|<span data-ttu-id="3b802-106">Член</span><span class="sxs-lookup"><span data-stu-id="3b802-106">Member</span></span>|<span data-ttu-id="3b802-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b802-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="3b802-108">Указывает Microsoft промежуточного языка MSIL индекс локальной переменной или параметра.</span><span class="sxs-lookup"><span data-stu-id="3b802-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="3b802-109">Указывает относительный виртуальный адрес в модуль.</span><span class="sxs-lookup"><span data-stu-id="3b802-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="3b802-110">Указывает регистр ЦП.</span><span class="sxs-lookup"><span data-stu-id="3b802-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="3b802-111">Указывает, что первый адрес является регистром, а второй — смещение.</span><span class="sxs-lookup"><span data-stu-id="3b802-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="3b802-112">Указывает смещение от базового адреса.</span><span class="sxs-lookup"><span data-stu-id="3b802-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="3b802-113">Указывает, что первый адрес является нижней частью регистра, а второй — верхней.</span><span class="sxs-lookup"><span data-stu-id="3b802-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="3b802-114">Указывает, что первый адрес является нижней частью регистра, второй — верхней и третий — это смещение.</span><span class="sxs-lookup"><span data-stu-id="3b802-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="3b802-115">Указывает, что первый адрес является регистром, второй — это смещение и третий — верхней регистра.</span><span class="sxs-lookup"><span data-stu-id="3b802-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="3b802-116">Указывает, что первый адрес является началом поля, а второй — длина поля.</span><span class="sxs-lookup"><span data-stu-id="3b802-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="3b802-117">Указывает, что первый адрес является раздел, а второй — смещение.</span><span class="sxs-lookup"><span data-stu-id="3b802-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b802-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3b802-118">Requirements</span></span>  
 <span data-ttu-id="3b802-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3b802-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b802-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3b802-120">See also</span></span>

- [<span data-ttu-id="3b802-121">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="3b802-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
