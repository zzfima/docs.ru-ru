---
title: Метод XmlReader. Креатесклреадер (System. XML)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582784"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="ae70d-102">XmlReader. Креатесклреадер, метод</span><span class="sxs-lookup"><span data-stu-id="ae70d-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="ae70d-103">Создает новый экземпляр <xref:System.Xml.XmlReader>, используя заданный поток, параметры и контекстную информацию для анализа.</span><span class="sxs-lookup"><span data-stu-id="ae70d-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="ae70d-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae70d-104">Parameters</span></span>

- <span data-ttu-id="ae70d-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="ae70d-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="ae70d-106">Поток, содержащий XML-данные.</span><span class="sxs-lookup"><span data-stu-id="ae70d-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="ae70d-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="ae70d-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="ae70d-108">Параметры нового экземпляра <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ae70d-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="ae70d-109">Это значение может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="ae70d-109">This value can be `null`.</span></span>

- <span data-ttu-id="ae70d-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="ae70d-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="ae70d-111">Для синтаксического анализа фрагмента XML необходимы контекстные сведения.</span><span class="sxs-lookup"><span data-stu-id="ae70d-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="ae70d-112">Это значение может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="ae70d-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="ae70d-113">Returns</span><span class="sxs-lookup"><span data-stu-id="ae70d-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="ae70d-114">Объект, используемый для чтения данных XML в потоке.</span><span class="sxs-lookup"><span data-stu-id="ae70d-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae70d-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="ae70d-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ae70d-116">Метод `XmlReader.CreateSqlReader` является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="ae70d-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ae70d-117">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="ae70d-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ae70d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ae70d-118">Requirements</span></span>

<span data-ttu-id="ae70d-119">**Пространство имен:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="ae70d-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="ae70d-120">**Сборка:** System. XML. dll</span><span class="sxs-lookup"><span data-stu-id="ae70d-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="ae70d-121">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="ae70d-121">**.NET Framework versions:** Available since 2.0.</span></span>
