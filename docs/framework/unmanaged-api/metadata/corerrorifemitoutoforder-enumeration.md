---
title: Перечисление CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628ca1b555d80319312450d784981cfed1bda947
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160450"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="9cf7a-102">Перечисление CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="9cf7a-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="9cf7a-103">Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cf7a-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="9cf7a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9cf7a-105">Members</span></span>  
  
|<span data-ttu-id="9cf7a-106">Член</span><span class="sxs-lookup"><span data-stu-id="9cf7a-106">Member</span></span>|<span data-ttu-id="9cf7a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9cf7a-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="9cf7a-108">Указывает поведение по умолчанию, которое не создает сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="9cf7a-109">Указывает, что компилятору не создавать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="9cf7a-110">Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выдается в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="9cf7a-111">Указывает, что компилятор должен создать сообщение об ошибке, когда метод выдается в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="9cf7a-112">Указывает, что компилятор должен создать сообщение об ошибке при извлечении поля по порядку.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="9cf7a-113">Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="9cf7a-114">Указывает, что компилятор должен создать сообщение об ошибке при извлечении свойства в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="9cf7a-115">Указывает, что компилятор должен создать сообщение об ошибке при извлечении неупорядоченных событий.</span><span class="sxs-lookup"><span data-stu-id="9cf7a-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cf7a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9cf7a-116">Requirements</span></span>  
 <span data-ttu-id="9cf7a-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf7a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf7a-118">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9cf7a-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9cf7a-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf7a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf7a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9cf7a-120">See also</span></span>

- [<span data-ttu-id="9cf7a-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="9cf7a-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
