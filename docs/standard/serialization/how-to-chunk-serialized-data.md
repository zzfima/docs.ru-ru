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
ms.openlocfilehash: 65e332d229da8fe51ad9c3e9850603471b1dfb12
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307240"
---
# <a name="how-to-chunk-serialized-data"></a>Практическое руководство. Фрагментация сериализованных данных

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

При отправке больших наборов данных в сообщениях веб-служб возникают две проблемы:  
  
1. Рабочий набор большого размера (память) из-за буферизации модулем сериализации.  
  
2. Чрезмерное потребление пропускной способности сети из-за 33-процентного увеличения после кодирования Base64.  
  
 Чтобы решить эти проблемы, реализуйте интерфейс <xref:System.Xml.Serialization.IXmlSerializable> для управления сериализацией и десериализацией. В частности, реализуйте методы <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> и <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> для фрагментации данных.  
  
### <a name="to-implement-server-side-chunking"></a>Реализация фрагментации на стороне сервера  
  
1. На сервере веб-метод должен отключать буферизацию ASP.NET и возвращать тип, реализующий <xref:System.Xml.Serialization.IXmlSerializable>.  
  
2. Тип, реализующий <xref:System.Xml.Serialization.IXmlSerializable>, фрагментирует данные в методе <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
### <a name="to-implement-client-side-processing"></a>Реализация обработки данных на стороне клиента  
  
1. Измените веб-метод на прокси клиента для возвращения типа, реализующего <xref:System.Xml.Serialization.IXmlSerializable>. Это можно сделать автоматически с помощью <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>, но в данном разделе это не представлено.  
  
2. Реализуйте метод <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> для чтения потока фрагментированных данных и записи байтов на диск. При такой реализации также создаются события о ходе выполнения операции, которые можно отображать графически, например, в индикаторе выполнения.  
  
## <a name="example"></a>Пример  
В следующем примере кода показан веб-метод на клиенте, который выключает буферизацию ASP.NET. В нем также показана реализация интерфейса <xref:System.Xml.Serialization.IXmlSerializable> на стороне клиента, при которой данные фрагментируются в методе <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   В коде используются следующие пространства имен: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> и <xref:System.Xml.Schema>.  
  
## <a name="see-also"></a>См. также

- [Пользовательская сериализация](custom-serialization.md)
