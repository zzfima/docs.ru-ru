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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160450"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="ca6ca-102">Перечисление CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="ca6ca-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="ca6ca-103">Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca6ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca6ca-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ca6ca-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ca6ca-105">Members</span></span>  
  
|<span data-ttu-id="ca6ca-106">Член</span><span class="sxs-lookup"><span data-stu-id="ca6ca-106">Member</span></span>|<span data-ttu-id="ca6ca-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca6ca-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="ca6ca-108">Указывает поведение по умолчанию, которое не создает сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="ca6ca-109">Указывает, что компилятору не создавать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="ca6ca-110">Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выдается в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="ca6ca-111">Указывает, что компилятор должен создать сообщение об ошибке, когда метод выдается в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="ca6ca-112">Указывает, что компилятор должен создать сообщение об ошибке при извлечении поля по порядку.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="ca6ca-113">Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="ca6ca-114">Указывает, что компилятор должен создать сообщение об ошибке при извлечении свойства в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="ca6ca-115">Указывает, что компилятор должен создать сообщение об ошибке при извлечении неупорядоченных событий.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca6ca-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ca6ca-116">Requirements</span></span>  
 <span data-ttu-id="ca6ca-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca6ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca6ca-118">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ca6ca-118">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="ca6ca-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ca6ca-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca6ca-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ca6ca-120">See also</span></span>

- [<span data-ttu-id="ca6ca-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ca6ca-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
