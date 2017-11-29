---
title: "Класс MissingInteropDataException (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0a7e1c02b6404f9511032d18f260726d1493d202
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="missinginteropdataexception-class-net-native"></a>Класс MissingInteropDataException (машинный код .NET)
**Приложения .NET для Windows 10, [!INCLUDE[net_native](../../../includes/net-native-md.md)] только**   
  
 Исключение, которое возникает, когда вызывается ручной метод маршалинга, но не найдены метаданные для типа в ходе статического анализа или в файле директив среды выполнения.  
  
 **Пространство имен:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
>  Класс `MissingInteropDataException` предназначен исключительно для внутреннего использования цепочкой инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Он не предназначен для использования в стороннем коде. Вам также не следует обрабатывать исключение в коде своего приложения. Вместо этого вы устраняете исключение, добавляя записи в [файл директив среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Дополнительные сведения см. в разделе "Примечания".  
  
## <a name="syntax"></a>Синтаксис  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 В классе `MissingInteropDataException`представлены следующие члены:  
  
## <a name="constructors"></a>Конструкторы  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Инициализирует новый экземпляр класса `MissingInteropDataException` с использованием идентификатора системного сообщения, описывающего ошибку и тип, данные которого отсутствуют. Этот конструктор предназначен только для внутреннего использования цепочки инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Возвращает коллекцию пар ключ/значение, предоставляющие дополнительные сведения об исключении, определяемые пользователем. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string HelpLink { get; set; }`|Получает или задает ссылку на файл справки, связанный с этим исключением. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int HResult { get; protected set; }`|Получает или задает `HRESULT`, который представляет собой закодированное числовое значение, присвоенное определенному исключению. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Exception InnerException { get; }`|Получает исключение, которое вызвало текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string Message { get; }`|Получает сообщение, описывающее текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Type MissingType { get; private set; }`|Получает или задает тип, для которого данные отсутствуют.|  
|`public string Source { get; set; }`|Получает или задает имя приложения или объекта, вызвавшего ошибку. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string StackTrace { get; }`|Получает строковое представление непосредственных кадров в стеке вызова. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public MethodBase TargetSite { get; }`|Возвращает метод, который вызвал текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Определяет, равен ли заданный объект текущему объекту.  (Является наследником <xref:System.Object>)|  
|`protected void Finalize()`|Позволяет объекту попытаться освободить ресурсы и выполнить другие операции очистки, перед тем как он будет уничтожен во время сборки мусора. (Является наследником <xref:System.Object>)|  
|`public Exception GetBaseException()`|Возвращает исключение, которое является корневой причиной одного или нескольких исключений. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int GetHashCode()`|Возвращает хэш-код для экземпляра`MissingInteropDataException`.   (Является наследником <xref:System.Object>)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Задает объект <xref:System.Runtime.Serialization.SerializationInfo>, содержащий информацию об исключении.  (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Type GetType()`|Возвращает тип среды выполнения текущего экземпляра. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`protected Object MemberwiseClone()`|Создает неполную копию текущего объекта. (Является наследником <xref:System.Object>)|  
|`public string ToString()`|Возвращает строковое представление текущего исключения. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="events"></a>События  
  
|Событие|Описание|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Возникает, когда исключение сериализовано для создания объекта состояния исключения, содержащего сериализованные данные об исключении. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="usage-details"></a>Сведения об использовании  
 Исключение `MissingInteropDataException` возникает, если вызов метода в компонент COM или среду выполнения Windows не удается выполнить успешно, поскольку информация о типе недоступна.  
  
 Метаданные, доступные для приложения во время выполнения определяются файлом директив среды выполнения (XML-файл конфигурации), *. rd.xml. Чтобы избежать возникновения этого исключения приложения, необходимо изменить этот файл для определения метаданных, которые должны присутствовать во время выполнения. Чаще всего, можно устранить эту ошибку путем добавления атрибута `MarshalObject`, `MarshalDelegate`, или `MarshalStructure` к соответствующему программному элементу файла директив среды выполнения. Сведения о формате этого файла см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Так как это исключение указывает, что метаданные, необходимые для приложения, недоступны во время выполнения, не следует обрабатывать это исключение в блоке `try`/`catch`. Вместо этого следует выяснить причину возникновения исключения и устранить ее, добавив соответствующую запись в файл директив среды выполнения.  
  
 Класс `MissingInteropDataException` содержит один уникальный член, свойство `MissingType`, указывающее тип, метаданные которого необходимы для успешного вызова метода. Все оставшиеся члены наследуются от базового класса, <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Exception?displayProperty=nameWithType>  
 [Класс MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
