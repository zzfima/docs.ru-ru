---
title: Сериализация — .NET
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053346"
---
# <a name="serialization-in-net"></a><span data-ttu-id="82d82-102">Сериализация в .NET</span><span class="sxs-lookup"><span data-stu-id="82d82-102">Serialization in .NET</span></span>

<span data-ttu-id="82d82-103">Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи.</span><span class="sxs-lookup"><span data-stu-id="82d82-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="82d82-104">Дополнением к сериализации служит десериализация, при которой осуществляется преобразование потока в объект.</span><span class="sxs-lookup"><span data-stu-id="82d82-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="82d82-105">Вместе эти процессы позволяют сохранять и передавать данные.</span><span class="sxs-lookup"><span data-stu-id="82d82-105">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="82d82-106">В .NET реализованы следующие технологии сериализации:</span><span class="sxs-lookup"><span data-stu-id="82d82-106">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="82d82-107">[Двоичная сериализация](binary-serialization.md) сохраняет точность типов, что полезно для сохранения состояния объекта между разными вызовами приложения.</span><span class="sxs-lookup"><span data-stu-id="82d82-107">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="82d82-108">Например, можно обеспечить совместный доступ к объекту для разных приложений, сериализовав его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="82d82-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="82d82-109">Объект можно сериализовать в поток, на диск, в память, передать по сети и т. д.</span><span class="sxs-lookup"><span data-stu-id="82d82-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="82d82-110">При удаленном управлении сериализация используется для передачи объектов "по значению" с одного компьютера или домена приложения на другой.</span><span class="sxs-lookup"><span data-stu-id="82d82-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="82d82-111">[Сериализация XML и SOAP](xml-and-soap-serialization.md) сериализует только открытые свойства и поля и не сохраняет точность типов.</span><span class="sxs-lookup"><span data-stu-id="82d82-111">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="82d82-112">Этот метод полезен для предоставления или использования данных без ограничений работающего с ними приложения.</span><span class="sxs-lookup"><span data-stu-id="82d82-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="82d82-113">Будучи открытым стандартом, XML привлекателен для совместного использования данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="82d82-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="82d82-114">Аналогичным образом и SOAP представляет собой открытый стандарт, использование которого эффективно и удобно.</span><span class="sxs-lookup"><span data-stu-id="82d82-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="82d82-115">[Сериализация JSON](system-text-json-overview.md) сериализует только открытые свойства и не сохраняет точность типов.</span><span class="sxs-lookup"><span data-stu-id="82d82-115">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="82d82-116">JSON — это открытый стандарт, который является привлекательным выбором для совместного использования данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="82d82-116">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="82d82-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="82d82-117">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="82d82-118">Содержит классы, которые можно использовать для сериализации и десериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="82d82-118">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="82d82-119">Содержит классы, которые можно использовать для сериализации объектов в документы формата XML или в потоки.</span><span class="sxs-lookup"><span data-stu-id="82d82-119">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="82d82-120">Содержит классы, которые можно использовать для сериализации объектов в документы или потоки формата JSON.</span><span class="sxs-lookup"><span data-stu-id="82d82-120">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
