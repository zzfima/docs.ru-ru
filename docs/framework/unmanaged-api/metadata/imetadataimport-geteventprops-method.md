---
title: Метод IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ac1ecb73257782888c963082953ed243177a86b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448808"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="bf1ef-102">Метод IMetaDataImport::GetEventProps</span><span class="sxs-lookup"><span data-stu-id="bf1ef-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="bf1ef-103">Возвращает сведения о метаданных для события, представленного указанным токеном события, включая объявляющий тип, добавления и методы удаления для делегатов и всевозможные флаги и другие связанные с ними данные.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf1ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf1ef-104">Syntax</span></span>  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf1ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf1ef-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="bf1ef-106">[in] Токен метаданных события, представляющий событие для получения метаданных для.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="bf1ef-107">[out] Указатель на токен TypeDef, представляющий класс, объявляющий событие.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="bf1ef-108">[out] Имя события, на который указывает `ev`.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="bf1ef-109">[in] Запрошенная длина в расширенных символах с `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="bf1ef-110">[out] Возвращаемая длина в расширенных символах с `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="bf1ef-111">[out] Указатель на объект TypeRef или TypeDef метаданных токен, представляющий <xref:System.Delegate> тип события.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="bf1ef-112">[out] Указатель на токен метаданных, представляющий метод, который добавляет обработчик для события.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="bf1ef-113">[out] Указатель на токен метаданных, представляющий метод, который удаляет обработчик для события.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="bf1ef-114">[out] Указатель на токен метаданных, представляющий метод, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="bf1ef-115">[out] Массив указателей токена в другие методы, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bf1ef-116">[in] Максимальный размер массива `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="bf1ef-117">[out] Число маркеров, возвращаемых в `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="bf1ef-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf1ef-118">Требования</span><span class="sxs-lookup"><span data-stu-id="bf1ef-118">Requirements</span></span>  
 <span data-ttu-id="bf1ef-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf1ef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf1ef-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf1ef-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf1ef-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf1ef-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf1ef-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf1ef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1ef-123">См. также</span><span class="sxs-lookup"><span data-stu-id="bf1ef-123">See Also</span></span>  
 [<span data-ttu-id="bf1ef-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bf1ef-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bf1ef-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bf1ef-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
