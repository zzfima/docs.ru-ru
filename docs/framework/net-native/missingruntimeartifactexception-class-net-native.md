---
title: Класс MissingRuntimeArtifactException (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: d5b3d13e-689f-4584-8ba6-44f5167a8590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7b138aec8a64683ca4b42cbbc8bd3584c06cc90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397053"
---
# <a name="missingruntimeartifactexception-class-net-native"></a>Класс MissingRuntimeArtifactException (машинный код .NET)
**Приложения .NET для Windows 10, [!INCLUDE[net_native](../../../includes/net-native-md.md)] только**   
  
 Исключение возникает, когда метаданные для типа или члена типа доступны, но его реализация была удалена.  
  
 **Пространство имен:** System.Reflection  
  
> [!IMPORTANT]
>  Класс `MissingRuntimeArtifactException` предназначен исключительно для внутреннего использования цепочкой инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Он не предназначен для использования в стороннем коде. Вам также не следует обрабатывать исключение в коде своего приложения. Вместо этого вы устраняете исключение, добавляя записи в [файл директив среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Дополнительные сведения см. в разделе "Примечания".  
  
## <a name="syntax"></a>Синтаксис  
 [!code-csharp[ProjectN#22](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingruntimeartifactexception_syntax1.cs#22)]  
  
 Обратите внимание на то, что класс `MissingRuntimeArtifactException` является производным от <xref:System.MemberAccessException>.  
  
 В классе `MissingRuntimeArtifactException`представлены следующие члены:  
  
## <a name="constructors"></a>Конструкторы  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`public MissingRuntimeArtifactException()`|Инициализирует новый экземпляр класса `MissingRuntimeArtifactException`, используя системное сообщение, содержащее описание ошибки.<br /><br /> Этот конструктор предназначен только для внутреннего использования цепочки инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
|`public MissingRuntimeArtifactException(String message)`|Инициализирует новый экземпляр класса `MissingRuntimeArtifactException` с указанным сообщением об ошибке.<br /><br /> Этот конструктор предназначен только для внутреннего использования цепочки инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Возвращает коллекцию пар ключ/значение, предоставляющие дополнительные сведения об исключении, определяемые пользователем. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string HelpLink { get; set; }`|Получает или задает ссылку на файл справки, связанный с этим исключением. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int HResult { get; protected set; }`|Получает или задает `HRESULT`, закодированное числовое значение, присвоенное определенному исключению. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Exception InnerException { get; }`|Получает исключение, которое вызвало текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string Message { get; }`|Получает сообщение, описывающее текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string Source { get; set; }`|Возвращает или задает имя приложения или объекта, вызвавшего ошибку. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public string StackTrace { get; }`|Получает строковое представление непосредственных кадров в стеке вызова. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public MethodBase TargetSite { get; }`|Возвращает метод, который вызвал текущее исключение. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Определяет, равен ли заданный объект текущему объекту.  (Является наследником <xref:System.Object>)|  
|`protected void Finalize()`|Позволяет объекту попытаться освободить ресурсы и выполнить другие операции очистки, перед тем как он будет уничтожен во время сборки мусора. (Является наследником <xref:System.Object>)|  
|`public Exception GetBaseException()`|Возвращает исключение, которое является корневой причиной одного или нескольких исключений. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public int GetHashCode()`|Возвращает хэш-код для экземпляра`MissingRuntimeArtifactException`.   (Является наследником <xref:System.Object>)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Задает объект <xref:System.Runtime.Serialization.SerializationInfo>, содержащий информацию об исключении.  (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`public Type GetType()`|Возвращает тип среды выполнения текущего экземпляра. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
|`protected Object MemberwiseClone()`|Создает неполную копию текущего объекта. (Является наследником <xref:System.Object>)|  
|`public string ToString()`|Возвращает строковое представление текущего исключения. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="events"></a>События  
  
|Событие|Описание|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Возникает, когда исключение сериализовано для создания объекта состояния исключения, содержащего сериализованные данные об исключении. (Является наследником <xref:System.Exception?displayProperty=nameWithType>)|  
  
## <a name="usage-details"></a>Сведения об использовании  
 Исключение `MissingRuntimeArtifactException`возникает при попытке создать экземпляр типа или вызвать член типа, и хотя метаданные типа или члена присутствуют, его реализация была удалена.  
  
 Доступность метаданных и кода реализации для динамического выполнения метода в приложении во время выполнения определяется файлом директив среды выполнения (XML-ФАЙЛ конфигурации), *. rd.xml. Чтобы избежать возникновения этого исключения в приложении, необходимо изменить файл \*.rd.xml, так чтобы метаданные, необходимые для типов и членов типов, были доступны во время выполнения. Сведения о формате файла rd.xml \* см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Так как это исключение указывает, что код реализации, необходимый для приложения, недоступен во время выполнения, не следует обрабатывать это исключение в блоке `try`/`catch`. Вместо этого следует выяснить причины возникновения исключения и устранить ее с помощью файла директив среды выполнения. Как правило, можно устранить это исключение, указав соответствующую политику `Activate` или `Dynamic` для программного элемента в файле директив среды выполнения (*. rd.xml файл). Чтобы получить запись, которую можно добавить в файл директив среды выполнения, устраняющий исключение, можно использовать одно из двух средств устранения неполадок.  
>   
>  -   [Средство устранения неполадок MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html) для типов.  
> -   [Средство устранения неполадок MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html) для методов.  
  
 Класс `MissingRuntimeArtifactException` не содержит уникальных членов; все его члены наследуются от базового класса, <xref:System.MemberAccessException>.  
  
## <a name="see-also"></a>См. также  
 [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
