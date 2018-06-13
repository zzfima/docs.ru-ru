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
ms.openlocfilehash: d4e9d03dcf4603f9470f8f2509050eb6f875746a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442644"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="d36ff-102">Перечисление CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="d36ff-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="d36ff-103">Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.</span><span class="sxs-lookup"><span data-stu-id="d36ff-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d36ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d36ff-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d36ff-105">Members</span></span>  
  
|<span data-ttu-id="d36ff-106">Член</span><span class="sxs-lookup"><span data-stu-id="d36ff-106">Member</span></span>|<span data-ttu-id="d36ff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d36ff-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="d36ff-108">Указывает поведение по умолчанию, которое не выдает сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d36ff-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="d36ff-109">Указывает, что компилятор не должен создавать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d36ff-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="d36ff-110">Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выпускаются в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="d36ff-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="d36ff-111">Указывает, что когда метод выдается вне очереди, компилятор должен создать сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d36ff-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="d36ff-112">Указывает, что компилятор должен создать сообщение об ошибке при поле выпускаются в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="d36ff-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="d36ff-113">Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.</span><span class="sxs-lookup"><span data-stu-id="d36ff-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="d36ff-114">Указывает, что когда свойство выдается вне очереди, компилятор должен создать сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d36ff-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="d36ff-115">Указывает, что компилятор должен создать сообщение об ошибке при извлечении события по порядку.</span><span class="sxs-lookup"><span data-stu-id="d36ff-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d36ff-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d36ff-116">Requirements</span></span>  
 <span data-ttu-id="d36ff-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d36ff-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36ff-118">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d36ff-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d36ff-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36ff-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36ff-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d36ff-120">See Also</span></span>  
 [<span data-ttu-id="d36ff-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d36ff-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
