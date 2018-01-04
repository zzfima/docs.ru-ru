---
title: "Интерфейс IMetaDataImport2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7cd9d2cd2837ff43fbb266717546db3aa98190e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="25b1e-102">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="25b1e-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="25b1e-103">Расширяет [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейса для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="25b1e-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25b1e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="25b1e-104">Methods</span></span>  
  
|<span data-ttu-id="25b1e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="25b1e-105">Method</span></span>|<span data-ttu-id="25b1e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="25b1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25b1e-107">Метод EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="25b1e-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="25b1e-108">Получает перечислитель для массива ограничений параметра универсального типа, связанный с универсальным параметром, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="25b1e-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="25b1e-109">Метод EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="25b1e-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="25b1e-110">Возвращает перечислитель для массива маркеров параметра универсального типа, связанный с указанным TypeDef или MethodDef, токен.</span><span class="sxs-lookup"><span data-stu-id="25b1e-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="25b1e-111">Метод EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="25b1e-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="25b1e-112">Возвращает перечислитель для массива маркеров MethodSpec, связанных с указанным MethodDef или MemberRef токен.</span><span class="sxs-lookup"><span data-stu-id="25b1e-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="25b1e-113">Метод GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="25b1e-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="25b1e-114">Возвращает метаданные, связанные с ограничением параметра универсального типа, представленного маркером указанное ограничение.</span><span class="sxs-lookup"><span data-stu-id="25b1e-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="25b1e-115">Метод GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="25b1e-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="25b1e-116">Возвращает метаданные, связанные с универсальным параметром, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="25b1e-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="25b1e-117">Метод GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="25b1e-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="25b1e-118">Возвращает подпись метаданных для метода, который ссылается указанный MethodSpec токен.</span><span class="sxs-lookup"><span data-stu-id="25b1e-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="25b1e-119">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="25b1e-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="25b1e-120">Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файла, обычно файл EXE или DLL, определенные в текущей области метаданных</span><span class="sxs-lookup"><span data-stu-id="25b1e-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="25b1e-121">Метод GetVersionString</span><span class="sxs-lookup"><span data-stu-id="25b1e-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="25b1e-122">Получает номер версии среды выполнения, который использовался для создания сборки.</span><span class="sxs-lookup"><span data-stu-id="25b1e-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25b1e-123">Требования</span><span class="sxs-lookup"><span data-stu-id="25b1e-123">Requirements</span></span>  
 <span data-ttu-id="25b1e-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25b1e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b1e-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25b1e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25b1e-126">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25b1e-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25b1e-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25b1e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b1e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="25b1e-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="25b1e-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="25b1e-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="25b1e-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="25b1e-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
