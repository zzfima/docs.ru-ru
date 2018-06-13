---
title: CorElementType Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebe2cf95f5637e6924b85c2389f1c59679580298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449174"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="17dae-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="17dae-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="17dae-103">Указывает, среда выполнения <xref:System.Type>, модификатор типа или сведения о типе в сигнатуре типа метаданных.</span><span class="sxs-lookup"><span data-stu-id="17dae-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17dae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17dae-104">Syntax</span></span>  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a><span data-ttu-id="17dae-105">Участники</span><span class="sxs-lookup"><span data-stu-id="17dae-105">Members</span></span>  
  
|<span data-ttu-id="17dae-106">Член</span><span class="sxs-lookup"><span data-stu-id="17dae-106">Member</span></span>|<span data-ttu-id="17dae-107">Описание</span><span class="sxs-lookup"><span data-stu-id="17dae-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="17dae-108">Используется внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="17dae-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="17dae-109">Значение типа void.</span><span class="sxs-lookup"><span data-stu-id="17dae-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="17dae-110">Логический тип.</span><span class="sxs-lookup"><span data-stu-id="17dae-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="17dae-111">Тип символа.</span><span class="sxs-lookup"><span data-stu-id="17dae-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="17dae-112">1-байтовое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="17dae-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="17dae-113">1-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="17dae-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="17dae-114">2-байтовое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="17dae-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="17dae-115">2-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="17dae-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="17dae-116">4-байтовое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="17dae-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="17dae-117">4-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="17dae-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="17dae-118">8-байтовое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="17dae-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="17dae-119">8-байтовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="17dae-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="17dae-120">4-байтовое число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="17dae-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="17dae-121">8-байтовое число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="17dae-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="17dae-122">Тип System.String.</span><span class="sxs-lookup"><span data-stu-id="17dae-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="17dae-123">Модификатор типа указателя.</span><span class="sxs-lookup"><span data-stu-id="17dae-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="17dae-124">Модификатор ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="17dae-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="17dae-125">Модификатор типа значения.</span><span class="sxs-lookup"><span data-stu-id="17dae-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="17dae-126">Модификатор типа класса.</span><span class="sxs-lookup"><span data-stu-id="17dae-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="17dae-127">Модификатор типа переменной.</span><span class="sxs-lookup"><span data-stu-id="17dae-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="17dae-128">Модификатор типа многомерного массива.</span><span class="sxs-lookup"><span data-stu-id="17dae-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="17dae-129">Модификатор типа для универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="17dae-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="17dae-130">Типизированная ссылка.</span><span class="sxs-lookup"><span data-stu-id="17dae-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="17dae-131">Размер собственного целого числа со знаком.</span><span class="sxs-lookup"><span data-stu-id="17dae-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="17dae-132">Размер собственного целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="17dae-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="17dae-133">Указатель на функцию.</span><span class="sxs-lookup"><span data-stu-id="17dae-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="17dae-134">Тип System.Object.</span><span class="sxs-lookup"><span data-stu-id="17dae-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="17dae-135">Одномерный, модификатор типа нулевой нижней границы массива.</span><span class="sxs-lookup"><span data-stu-id="17dae-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="17dae-136">Модификатор типа переменной метода.</span><span class="sxs-lookup"><span data-stu-id="17dae-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="17dae-137">Обязательный модификатор языка c.</span><span class="sxs-lookup"><span data-stu-id="17dae-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="17dae-138">Необязательный модификатор языка C.</span><span class="sxs-lookup"><span data-stu-id="17dae-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="17dae-139">Используется внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="17dae-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="17dae-140">Недопустимый тип.</span><span class="sxs-lookup"><span data-stu-id="17dae-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="17dae-141">Используется внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="17dae-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="17dae-142">Модификатор типа, который является sentinel список переменное количество параметров.</span><span class="sxs-lookup"><span data-stu-id="17dae-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="17dae-143">Используется внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="17dae-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17dae-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="17dae-144">Remarks</span></span>  
 <span data-ttu-id="17dae-145">Модификаторы типов образуют основу для представления более сложных типов.</span><span class="sxs-lookup"><span data-stu-id="17dae-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="17dae-146">Объект `CorElementType` значение модификатора типа применяется к значению, немедленно следующий за ним в сигнатуре типа.</span><span class="sxs-lookup"><span data-stu-id="17dae-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="17dae-147">Значение, которое следует за `CorElementType` значение модификатора типа может быть `CorElementType` значение простого типа, маркер метаданных или другое значение, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="17dae-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17dae-148">Все числа (*номер*, *счетчик аргументов*, *токен метаданных*, *ранг*, *число*и *привязан*) хранятся в виде сжатых целых чисел.</span><span class="sxs-lookup"><span data-stu-id="17dae-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="17dae-149">В разделе [стандарту ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) на сайте ECMA подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="17dae-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="17dae-150">Модификатор типа</span><span class="sxs-lookup"><span data-stu-id="17dae-150">Type modifier</span></span>|<span data-ttu-id="17dae-151">Формат</span><span class="sxs-lookup"><span data-stu-id="17dae-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="17dae-152">ELEMENT_TYPE_PTR < `CorElementType` значение ></span><span class="sxs-lookup"><span data-stu-id="17dae-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="17dae-153">ELEMENT_TYPE_BYREF < `CorElementType` значение ></span><span class="sxs-lookup"><span data-stu-id="17dae-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="17dae-154">ELEMENT_TYPE_VALUETYPE < `mdTypeDef` токен метаданных ></span><span class="sxs-lookup"><span data-stu-id="17dae-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="17dae-155">ELEMENT_TYPE_CLASS < `mdTypeDef` токен метаданных ></span><span class="sxs-lookup"><span data-stu-id="17dae-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="17dae-156">ELEMENT_TYPE_VAR \<число ></span><span class="sxs-lookup"><span data-stu-id="17dae-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="17dae-157">ELEMENT_TYPE_ARRAY < `CorElementType` значение > \<ранг > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="17dae-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="17dae-158">ELEMENT_TYPE_GENERICINST < `mdTypeDef` токен метаданных > \<аргумент Count > \<аргумент1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="17dae-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="17dae-159">ELEMENT_TYPE_FNPTR \<Полная сигнатура для функции, включая соглашение о вызовах ></span><span class="sxs-lookup"><span data-stu-id="17dae-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="17dae-160">ELEMENT_TYPE_SZARRAY < `CorElementType` значение ></span><span class="sxs-lookup"><span data-stu-id="17dae-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="17dae-161">ELEMENT_TYPE_MVAR \<число ></span><span class="sxs-lookup"><span data-stu-id="17dae-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="17dae-162">ELEMENT_TYPE_ < `mdTypeRef` или `mdTypeDef` токен метаданных ></span><span class="sxs-lookup"><span data-stu-id="17dae-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="17dae-163">E_T_CMOD_OPT < `mdTypeRef` или `mdTypeDef` токен метаданных ></span><span class="sxs-lookup"><span data-stu-id="17dae-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17dae-164">Требования</span><span class="sxs-lookup"><span data-stu-id="17dae-164">Requirements</span></span>  
 <span data-ttu-id="17dae-165">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17dae-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17dae-166">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="17dae-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="17dae-167">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17dae-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17dae-168">См. также</span><span class="sxs-lookup"><span data-stu-id="17dae-168">See Also</span></span>  
 [<span data-ttu-id="17dae-169">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="17dae-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
