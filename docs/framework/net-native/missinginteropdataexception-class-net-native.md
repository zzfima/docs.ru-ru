---
title: Класс MissingInteropDataException (машинный код .NET)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
ms.openlocfilehash: faf14245cd9dd7aa4bf8e89d5a05901279956509
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128269"
---
# <a name="missinginteropdataexception-class-net-native"></a>Класс MissingInteropDataException (машинный код .NET)
**.NET для приложений Windows для Windows 10, только .NET Native**  
  
 Исключение, которое возникает, когда вызывается ручной метод маршалинга, но не найдены метаданные для типа в ходе статического анализа или в файле директив среды выполнения.  
  
 **Пространство имен:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
> Класс `MissingInteropDataException` предназначен исключительно для внутреннего использования в цепочке средств .NET Native. Он не предназначен для использования в стороннем коде. Вам также не следует обрабатывать исключение в коде своего приложения. Вместо этого вы устраняете исключение, добавляя записи в [файл директив среды выполнения](runtime-directives-rd-xml-configuration-file-reference.md). Дополнительные сведения см. в разделе "Примечания".  
  
## <a name="syntax"></a>Синтаксис  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 В классе `MissingInteropDataException`представлены следующие члены:  
  
## <a name="constructors"></a>Конструкторы  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Инициализирует новый экземпляр класса `MissingInteropDataException` с использованием идентификатора системного сообщения, описывающего ошибку и тип, данные которого отсутствуют. Этот конструктор предназначен только для внутреннего использования в цепочке средств .NET Native.|  
  
## <a name="properties"></a>Свойства  
  
|свойство;|Описание|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Возвращает коллекцию пар ключ/значение, предоставляющие дополнительные сведения об исключении, определяемые пользователем. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string HelpLink { get; set; }`|Получает или задает ссылку на файл справки, связанный с этим исключением. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int HResult { get; protected set; }`|Получает или задает `HRESULT`, который представляет собой закодированное числовое значение, присвоенное определенному исключению. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Exception InnerException { get; }`|Получает исключение, которое вызвало текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string Message { get; }`|Возвращает сообщение, описывающее текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Type MissingType { get; private set; }`|Получает или задает тип, для которого данные отсутствуют.|  
|`public string Source { get; set; }`|Получает или задает имя приложения или объекта, вызвавшего ошибку. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string StackTrace { get; }`|Получает строковое представление непосредственных кадров в стеке вызова. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public MethodBase TargetSite { get; }`|Возвращает метод, который вызвал текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Определяет, равен ли заданный объект текущему объекту.  (Является наследником <xref:System.Object>)|  
|`protected void Finalize()`|Позволяет объекту попытаться освободить ресурсы и выполнить другие операции очистки, перед тем как он будет уничтожен во время сборки мусора. (Является наследником <xref:System.Object>)|  
|`public Exception GetBaseException()`|Возвращает исключение, которое является первопричиной одного или нескольких исключений. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int GetHashCode()`|Возвращает хэш-код для экземпляра`MissingInteropDataException`.   (Является наследником <xref:System.Object>)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Задает объект <xref:System.Runtime.Serialization.SerializationInfo>, содержащий информацию об исключении.  (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Type GetType()`|Возвращает тип среды выполнения текущего экземпляра. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`protected Object MemberwiseClone()`|Создает неполную копию текущего объекта. (Является наследником <xref:System.Object>)|  
|`public string ToString()`|Возвращает строковое представление текущего исключения. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="events"></a>события  
  
|событие|Описание|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Возникает, когда исключение сериализовано для создания объекта состояния исключения, содержащего сериализованные данные об исключении. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="usage-details"></a>Сведения об использовании  
 Исключение `MissingInteropDataException` возникает, если вызов метода в компонент COM или среду выполнения Windows не удается выполнить успешно, поскольку информация о типе недоступна.  
  
 Метаданные, доступные для приложения во время выполнения, определяются в файле конфигурации директив среды выполнения (XML), \*. Rd. XML. Чтобы избежать возникновения этого исключения приложения, необходимо изменить этот файл для определения метаданных, которые должны присутствовать во время выполнения. Чаще всего, можно устранить эту ошибку путем добавления атрибута `MarshalObject`, `MarshalDelegate`, или `MarshalStructure` к соответствующему программному элементу файла директив среды выполнения. Сведения о формате этого файла см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
> Так как это исключение указывает, что метаданные, необходимые для приложения, недоступны во время выполнения, не следует обрабатывать это исключение в блоке `try`/`catch`. Вместо этого следует выяснить причину возникновения исключения и устранить ее, добавив соответствующую запись в файл директив среды выполнения.  
  
 Класс `MissingInteropDataException` содержит один уникальный член, свойство `MissingType`, указывающее тип, метаданные которого необходимы для успешного вызова метода. Все оставшиеся члены наследуются от базового класса, <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Exception?displayProperty=nameWithType>
- [Класс MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
