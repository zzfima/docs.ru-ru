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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897e396424b9076da8f30c61b5a14cfa9539690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795417"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="76a35-102">Перечисление CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="76a35-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="76a35-103">Задает атрибуты объекта [интерфейса IAssemblyName](iassemblyname-interface.md) при создании с помощью функции [креатеассемблинамеобжект](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="76a35-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76a35-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="76a35-105">Участники</span><span class="sxs-lookup"><span data-stu-id="76a35-105">Members</span></span>  
  
|<span data-ttu-id="76a35-106">Член</span><span class="sxs-lookup"><span data-stu-id="76a35-106">Member</span></span>|<span data-ttu-id="76a35-107">Описание</span><span class="sxs-lookup"><span data-stu-id="76a35-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="76a35-108">Указывает, что переданный параметр является текстовым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="76a35-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="76a35-109">Задает несколько значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76a35-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="76a35-110">Проверяет правило дружественной сборки (только имя и открытый ключ).</span><span class="sxs-lookup"><span data-stu-id="76a35-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="76a35-111">Этот член предназначен только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="76a35-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="76a35-112">Сочетание `CANOF_PARSE_DISPLAY_NAME` флагов и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` .</span><span class="sxs-lookup"><span data-stu-id="76a35-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="76a35-113">Этот член предназначен только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="76a35-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76a35-114">Требования</span><span class="sxs-lookup"><span data-stu-id="76a35-114">Requirements</span></span>  
 <span data-ttu-id="76a35-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76a35-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76a35-116">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="76a35-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="76a35-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a35-118">См. также</span><span class="sxs-lookup"><span data-stu-id="76a35-118">See also</span></span>

- [<span data-ttu-id="76a35-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="76a35-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="76a35-120">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="76a35-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="76a35-121">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="76a35-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
