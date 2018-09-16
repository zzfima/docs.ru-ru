---
title: Практическое руководство. Фрагментация сериализованных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- chunking serialized data
- data chunking
- binary serialization, chunking data
- large data set chunking
- serialization, chunking data
- serialization, examples
- binary serialization, examples
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
ms.openlocfilehash: 4b83e841db1afc898c5c3c99ed4186fd264ed2ef
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676549"
---
# <a name="how-to-chunk-serialized-data"></a><span data-ttu-id="497d5-102">Практическое руководство. Фрагментация сериализованных данных</span><span class="sxs-lookup"><span data-stu-id="497d5-102">How to: chunk serialized data</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="497d5-103">При отправке больших наборов данных в сообщениях веб-служб возникают две проблемы:</span><span class="sxs-lookup"><span data-stu-id="497d5-103">Two issues that occur when sending large data sets in Web service messages are:</span></span>  
  
1.  <span data-ttu-id="497d5-104">Рабочий набор большого размера (память) из-за буферизации модулем сериализации.</span><span class="sxs-lookup"><span data-stu-id="497d5-104">A large working set (memory) due to buffering by the serialization engine.</span></span>  
  
2.  <span data-ttu-id="497d5-105">Чрезмерное потребление пропускной способности сети из-за 33-процентного увеличения после кодирования Base64.</span><span class="sxs-lookup"><span data-stu-id="497d5-105">Inordinate bandwidth consumption due to 33 percent inflation after Base64 encoding.</span></span>  
  
 <span data-ttu-id="497d5-106">Чтобы решить эти проблемы, реализуйте интерфейс <xref:System.Xml.Serialization.IXmlSerializable> для управления сериализацией и десериализацией.</span><span class="sxs-lookup"><span data-stu-id="497d5-106">To solve these problems, implement the <xref:System.Xml.Serialization.IXmlSerializable> interface to control the serialization and deserialization.</span></span> <span data-ttu-id="497d5-107">В частности, реализуйте методы <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> и <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> для фрагментации данных.</span><span class="sxs-lookup"><span data-stu-id="497d5-107">Specifically, implement the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> and <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> methods to chunk the data.</span></span>  
  
### <a name="to-implement-server-side-chunking"></a><span data-ttu-id="497d5-108">Реализация фрагментации на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="497d5-108">To implement server-side chunking</span></span>  
  
1.  <span data-ttu-id="497d5-109">На сервере веб-метод должен отключать буферизацию ASP.NET и возвращать тип, реализующий <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="497d5-109">On the server machine, the Web method must turn off ASP.NET buffering and return a type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
2.  <span data-ttu-id="497d5-110">Тип, реализующий <xref:System.Xml.Serialization.IXmlSerializable>, фрагментирует данные в методе <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="497d5-110">The type that implements <xref:System.Xml.Serialization.IXmlSerializable> chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
### <a name="to-implement-client-side-processing"></a><span data-ttu-id="497d5-111">Реализация обработки данных на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="497d5-111">To implement client-side processing</span></span>  
  
1.  <span data-ttu-id="497d5-112">Измените веб-метод на прокси клиента для возвращения типа, реализующего <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="497d5-112">Alter the Web method on the client proxy to return the type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="497d5-113">Это можно сделать автоматически с помощью <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>, но в данном разделе это не представлено.</span><span class="sxs-lookup"><span data-stu-id="497d5-113">You can use a <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> to do this automatically, but this isn't shown here.</span></span>  
  
2.  <span data-ttu-id="497d5-114">Реализуйте метод <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> для чтения потока фрагментированных данных и записи байтов на диск.</span><span class="sxs-lookup"><span data-stu-id="497d5-114">Implement the <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> method to read the chunked data stream and write the bytes to disk.</span></span> <span data-ttu-id="497d5-115">При такой реализации также создаются события о ходе выполнения операции, которые можно отображать графически, например, в индикаторе выполнения.</span><span class="sxs-lookup"><span data-stu-id="497d5-115">This implementation also raises progress events that can be used by a graphic control, such as a progress bar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="497d5-116">Пример</span><span class="sxs-lookup"><span data-stu-id="497d5-116">Example</span></span>  
<span data-ttu-id="497d5-117">В следующем примере кода показан веб-метод на клиенте, который выключает буферизацию ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="497d5-117">The following code example shows the Web method on the client that turns off ASP.NET buffering.</span></span> <span data-ttu-id="497d5-118">В нем также показана реализация интерфейса <xref:System.Xml.Serialization.IXmlSerializable> на стороне клиента, при которой данные фрагментируются в методе <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="497d5-118">It also shows the client-side implementation of the <xref:System.Xml.Serialization.IXmlSerializable> interface that chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="497d5-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="497d5-119">Compiling the code</span></span>  
  
-   <span data-ttu-id="497d5-120">В коде используются следующие пространства имен: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> и <xref:System.Xml.Schema>.</span><span class="sxs-lookup"><span data-stu-id="497d5-120">The code uses the following namespaces: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, and <xref:System.Xml.Schema>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497d5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="497d5-121">See also</span></span>

- [<span data-ttu-id="497d5-122">Пользовательская сериализация</span><span class="sxs-lookup"><span data-stu-id="497d5-122">Custom Serialization</span></span>](custom-serialization.md)
