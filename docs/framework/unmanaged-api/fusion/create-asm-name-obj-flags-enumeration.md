---
title: Перечисление CREATE_ASM_NAME_OBJ_FLAGS
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: f6abb59c3aaec40a4e7b228b8c69147a2d454431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108885"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="b2159-102">Перечисление CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b2159-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="b2159-103">Задает атрибуты объекта [интерфейса IAssemblyName](iassemblyname-interface.md) при создании с помощью функции [креатеассемблинамеобжект](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b2159-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2159-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2159-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b2159-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b2159-105">Members</span></span>  
  
|<span data-ttu-id="b2159-106">Член</span><span class="sxs-lookup"><span data-stu-id="b2159-106">Member</span></span>|<span data-ttu-id="b2159-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b2159-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="b2159-108">Указывает, что переданный параметр является текстовым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="b2159-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="b2159-109">Задает несколько значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2159-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="b2159-110">Проверяет правило дружественной сборки (только имя и открытый ключ).</span><span class="sxs-lookup"><span data-stu-id="b2159-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="b2159-111">Этот член предназначен только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="b2159-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="b2159-112">Сочетание флагов `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME`.</span><span class="sxs-lookup"><span data-stu-id="b2159-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="b2159-113">Этот член предназначен только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="b2159-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2159-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b2159-114">Requirements</span></span>  
 <span data-ttu-id="b2159-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2159-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2159-116">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b2159-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b2159-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2159-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2159-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b2159-118">See also</span></span>

- [<span data-ttu-id="b2159-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b2159-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="b2159-120">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="b2159-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="b2159-121">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="b2159-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
