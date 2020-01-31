---
title: Соглашения о написании прописными буквами
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741761"
---
# <a name="capitalization-conventions"></a>Соглашения о написании прописными буквами
Рекомендации в этой главе посвящены созданию простого метода использования, который при единообразном применении делает идентификаторы для типов, членов и параметров простыми для чтения.

## <a name="capitalization-rules-for-identifiers"></a>Правила использования прописных букв для идентификаторов
 Чтобы отличать слова в идентификаторе, используйте прописные буквы первой буквы каждого слова в идентификаторе. Не используйте знаки подчеркивания для различения слов, а также для любого значения в любом месте идентификаторов. Существует два способа для капитализации идентификаторов в зависимости от использования идентификатора.

- паскалкасинг

- камелкасинг

 Соглашение Паскалкасинг, используемое для всех идентификаторов, кроме имен параметров, состоит из первых букв каждого слова (включая акронимы длиной более двух букв), как показано в следующих примерах:

 `PropertyDescriptor`
 `HtmlTag`

 Для акронимов с двумя буквами используется специальный случай, в котором буквы записываются прописными буквами, как показано в следующем идентификаторе:

 `IOStream`

 Соглашение Камелкасинг, используемое только для имен параметров, состоит из первых букв каждого слова, за исключением первого слова, как показано в следующих примерах. Как показано в примере, аббревиатуры с двумя буквами, начинающиеся с символов в стиле Camel, являются строчными.

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 ✔️ использовать Паскалкасинг для всех имен открытых членов, типов и пространств имен, состоящих из нескольких слов.

 ✔️ использовать Камелкасинг для имен параметров.

 В следующей таблице описаны правила капитализации для различных типов идентификаторов.

|Идентификатор|Различает|Пример|
|----------------|------------|-------------|
|Пространство имен|Pascal|`namespace System.Security { ... }`|
|Тип|Pascal|`public class StreamReader { ... }`|
|Интерфейс|Pascal|`public interface IEnumerable { ... }`|
|Метод|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|Идентификаторы|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|Event|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|Поле|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|Значение перечисления|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|Параметр|Нижнем|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a>Преобразование сложных слов и общих терминов в прописные
 Большинство составных терминов рассматриваются как отдельные слова в целях капитализации.

 ❌ не заменяйте каждое слово на прописные, так называемые составные слова с закрытыми формами.

 Это составные слова, написанные как одно слово, например конечная точка. В соответствии с рекомендациями по регистру рассматривайте составное слово с закрытой формой как одно слово. Используйте текущий словарь, чтобы определить, написано ли составное слово в закрытой форме.

|Pascal|Нижнем|not|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a>Учет регистра
 Языки, которые могут выполняться в среде CLR, не должны поддерживать чувствительность к регистру, хотя и некоторые. Даже если ваш язык поддерживает, другие языки, которые могут получить доступ к вашей платформе, не поддерживаются. Все интерфейсы API, доступ к которым осуществляется извне, поэтому не могут полагаться только на регистр, чтобы различать два имени в одном контексте.

 ❌ не предполагается, что все языки программирования чувствительны к регистру. Это не так. Имена не могут отличаться только регистром.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
