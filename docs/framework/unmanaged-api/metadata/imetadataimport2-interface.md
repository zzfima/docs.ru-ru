---
title: Интерфейс IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211937"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="df08c-102">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="df08c-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="df08c-103">Расширяет [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейса для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="df08c-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df08c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="df08c-104">Methods</span></span>  
  
|<span data-ttu-id="df08c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="df08c-105">Method</span></span>|<span data-ttu-id="df08c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="df08c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df08c-107">Метод EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="df08c-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="df08c-108">Получает перечислитель для массива универсальный параметр ограничения, связанные с универсального параметра, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="df08c-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="df08c-109">Метод EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="df08c-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="df08c-110">Получает перечислитель для массива маркеров параметра универсального типа, связанный с указанным TypeDef или MethodDef маркер.</span><span class="sxs-lookup"><span data-stu-id="df08c-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="df08c-111">Метод EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="df08c-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="df08c-112">Получает перечислитель для массива MethodSpec токенов, связанных с указанным MethodDef или MemberRef маркер.</span><span class="sxs-lookup"><span data-stu-id="df08c-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="df08c-113">Метод GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="df08c-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="df08c-114">Получает метаданные, связанные с ограничением параметра универсального типа, представленного маркером указанное ограничение.</span><span class="sxs-lookup"><span data-stu-id="df08c-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="df08c-115">Метод GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="df08c-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="df08c-116">Получает метаданные, связанные с универсального параметра, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="df08c-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="df08c-117">Метод GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="df08c-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="df08c-118">Получает токен метода, который ссылается указанный MethodSpec подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="df08c-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="df08c-119">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="df08c-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="df08c-120">Получает значение, определяющее природу кода в переносимом исполняемом (PE) файла, обычно файл EXE или DLL, определенных в текущей области метаданных</span><span class="sxs-lookup"><span data-stu-id="df08c-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="df08c-121">Метод GetVersionString</span><span class="sxs-lookup"><span data-stu-id="df08c-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="df08c-122">Получает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="df08c-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df08c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="df08c-123">Requirements</span></span>  
 <span data-ttu-id="df08c-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df08c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df08c-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df08c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df08c-126">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df08c-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df08c-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df08c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df08c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="df08c-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="df08c-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="df08c-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="df08c-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="df08c-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
