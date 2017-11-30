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
ms.openlocfilehash: 1b00879f1d22d49e5f0dc3bdb072e0545feda68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="87772-102">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="87772-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="87772-103">Расширяет [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейса для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="87772-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87772-104">Методы</span><span class="sxs-lookup"><span data-stu-id="87772-104">Methods</span></span>  
  
|<span data-ttu-id="87772-105">Метод</span><span class="sxs-lookup"><span data-stu-id="87772-105">Method</span></span>|<span data-ttu-id="87772-106">Описание</span><span class="sxs-lookup"><span data-stu-id="87772-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87772-107">Метод EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="87772-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="87772-108">Получает перечислитель для массива ограничений параметра универсального типа, связанный с универсальным параметром, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="87772-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="87772-109">Метод EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="87772-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="87772-110">Возвращает перечислитель для массива маркеров параметра универсального типа, связанный с указанным TypeDef или MethodDef, токен.</span><span class="sxs-lookup"><span data-stu-id="87772-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="87772-111">Метод EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="87772-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="87772-112">Возвращает перечислитель для массива маркеров MethodSpec, связанных с указанным MethodDef или MemberRef токен.</span><span class="sxs-lookup"><span data-stu-id="87772-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="87772-113">Метод GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="87772-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="87772-114">Возвращает метаданные, связанные с ограничением параметра универсального типа, представленного маркером указанное ограничение.</span><span class="sxs-lookup"><span data-stu-id="87772-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="87772-115">Метод GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="87772-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="87772-116">Возвращает метаданные, связанные с универсальным параметром, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="87772-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="87772-117">Метод GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="87772-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="87772-118">Возвращает подпись метаданных для метода, который ссылается указанный MethodSpec токен.</span><span class="sxs-lookup"><span data-stu-id="87772-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="87772-119">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="87772-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="87772-120">Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файла, обычно файл EXE или DLL, определенные в текущей области метаданных</span><span class="sxs-lookup"><span data-stu-id="87772-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="87772-121">Метод GetVersionString</span><span class="sxs-lookup"><span data-stu-id="87772-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="87772-122">Получает номер версии среды выполнения, который использовался для создания сборки.</span><span class="sxs-lookup"><span data-stu-id="87772-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87772-123">Требования</span><span class="sxs-lookup"><span data-stu-id="87772-123">Requirements</span></span>  
 <span data-ttu-id="87772-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87772-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87772-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="87772-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87772-126">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87772-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87772-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87772-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87772-128">См. также</span><span class="sxs-lookup"><span data-stu-id="87772-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="87772-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="87772-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="87772-130">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="87772-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
