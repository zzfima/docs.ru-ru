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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177271"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="eae2b-102">Метод IMetaDataImport::GetEventProps</span><span class="sxs-lookup"><span data-stu-id="eae2b-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="eae2b-103">Получает информацию о метаданных для события, представленную указанным маркером события, включая тип декларирования, способы добавления и удаления для делегатов, а также любые флаги и другие связанные данные.</span><span class="sxs-lookup"><span data-stu-id="eae2b-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eae2b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="eae2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eae2b-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="eae2b-106">(в) Токен метаданных события, представляющий событие для получения метаданных.</span><span class="sxs-lookup"><span data-stu-id="eae2b-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="eae2b-107">(ваут) Указатель на маркер TypeDef, представляющий класс, объявляющий событие.</span><span class="sxs-lookup"><span data-stu-id="eae2b-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="eae2b-108">(ваут) Название события, на которое `ev`ссылается .</span><span class="sxs-lookup"><span data-stu-id="eae2b-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="eae2b-109">(в) Запрошенная длина в широких `szEvent`символах .</span><span class="sxs-lookup"><span data-stu-id="eae2b-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="eae2b-110">(ваут) Возвращается длина в `szEvent`широких символов .</span><span class="sxs-lookup"><span data-stu-id="eae2b-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="eae2b-111">(ваут) Указатель на маркер метаданных TypeRef или TypeDef, представляющий <xref:System.Delegate> тип события.</span><span class="sxs-lookup"><span data-stu-id="eae2b-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="eae2b-112">(ваут) Указатель на маркер метаданных, представляющий метод, который добавляет обработчики для события.</span><span class="sxs-lookup"><span data-stu-id="eae2b-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="eae2b-113">(ваут) Указатель на маркер метаданных, представляющий метод, удаляющий обработчики для события.</span><span class="sxs-lookup"><span data-stu-id="eae2b-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="eae2b-114">(ваут) Указатель на маркер метаданных, представляющий метод, повысивший событие.</span><span class="sxs-lookup"><span data-stu-id="eae2b-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="eae2b-115">(ваут) Массив указателей токенов на другие методы, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="eae2b-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eae2b-116">[in] Максимальный размер массива `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="eae2b-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="eae2b-117">(ваут) Количество возвращенных токенов `rmdOtherMethod`в .</span><span class="sxs-lookup"><span data-stu-id="eae2b-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae2b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="eae2b-118">Requirements</span></span>  
 <span data-ttu-id="eae2b-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae2b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae2b-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eae2b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eae2b-121">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eae2b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eae2b-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae2b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae2b-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eae2b-123">See also</span></span>

- [<span data-ttu-id="eae2b-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="eae2b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eae2b-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="eae2b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
