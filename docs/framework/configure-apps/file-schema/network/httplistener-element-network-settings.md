---
title: '&lt;httpListener&gt; (сетевые параметры)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3daf18fab81ea481be8e45e4d9ad682047ada6f3
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50042640"
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;httpListener&gt; (сетевые параметры)
Настраивает параметры, используемые <xref:System.Net.HttpListener> класса.  
  
 \<configuration>  
\<System.NET >  
\<Параметры >  
\<httpListener >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Тип  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|unescapeRequestUrl|Логическое значение, указывающее, если <xref:System.Net.HttpListener> экземпляр использует преобразованный в escape-последовательность URI вместо преобразованного.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 **UnescapeRequestUrl** атрибут указывает, если <xref:System.Net.HttpListener> использует преобразованный в escape-последовательность URI вместо преобразованного где преобразуются значения, закодированные и других нормализации действия предпринимаются.  
  
 Когда <xref:System.Net.HttpListener> экземпляр получает запрос через `http.sys` службы, она создает экземпляр в строке URI, предоставляемые `http.sys`и предоставляет его как <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> свойство.  
  
 `http.sys` Служба предоставляет две строки URI запроса:  
  
-   Преобразованный в URI  
  
-   Преобразованный URI  
  
 Необработанный URL-адрес является <xref:System.Uri?displayProperty=nameWithType> в строке запроса HTTP-запроса:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Преобразованный в URI, предоставляемые `http.sys` для запроса, упомянутого выше, является «/ path /». Представляет строку, следующую команду HTTP, так как он был отправлен по сети.  
  
 `http.sys` Служба создает преобразованный URI из сведений, предоставленных в запросе с помощью URI, предоставленный в строке запроса HTTP и должны быть переадресованы заголовок узла для определения сервера-источника запроса. Это делается путем сравнения сведений из запроса с помощью набора зарегистрированных префиксов URI. В документации пакета SDK сервера HTTP ссылается на этот преобразованный URI как HTTP_COOKED_URL структуры.  
  
 Чтобы иметь возможность сравнить запрос с зарегистрированными префиксами URI, необходимо сделать некоторые нормализацию в запросе. Для примера выше преобразованный URI будет выглядеть следующим образом:  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` Службы объединяет <xref:System.Uri.Host%2A?displayProperty=nameWithType> значение свойства и строку в строку запроса для создания преобразованный URI. Кроме того `http.sys` и <xref:System.Uri?displayProperty=nameWithType> класс также выполняет следующее:  
  
-   Отмена переходов все процентные значения.  
  
-   Преобразует закодированные символы не из набора ASCII в представление символов UTF-16. Обратите внимание на то, что символы UTF-8 и ANSI/DBCS поддерживаются, а также символы Юникода (кодировка Юникод с использованием формата % uXXXX).  
  
-   Выполняет другие действия нормализации, такие как сжатие пути.  
  
 Так как запрос не содержит никакой информации о кодировку, используемую для значения, закодированные процентами, может оказаться невозможно определить правильную кодировку просто, путем синтаксического анализа закодированные значения.  
  
 Таким образом `http.sys` предоставляет два раздела реестра для изменения процесса:  
  
|Раздел реестра .|Значение по умолчанию|Описание|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Если значение равно нулю, `http.sys` принимает только URL-адреса в кодировке UTF-8.<br /><br /> Если ненулевое значение, `http.sys` также принимает URL-адреса в кодировке ANSI или кодировке (DBCS) в запросах.|  
|FavorUTF8|1|Если ненулевое значение, `http.sys` всегда пытается декодировать URL-адрес как UTF-8; Если это преобразование завершается неудачей и EnableNonUTF8 не равно нулю, Http.sys, а затем пытается декодировать его как ANSI или DBCS.<br /><br /> Если значение равно нулю (и EnableNonUTF8 не равно нулю), `http.sys` пытается декодировать его как ANSI или DBCS; Если это не обнаруживаются, осуществляется попытка преобразования UTF-8.|  
  
 Когда <xref:System.Net.HttpListener> получает запрос, он использует URI, преобразованное из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойство.  
  
 Нет необходимости поддерживать символы помимо символов и цифр в URI. Например, следующий URI, который используется для получения данных о заказчике для клиента номер «1/3812»:  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Обратите внимание, закодированные процентами косую черту в Uri (% 2F). Это необходимо, так как в этом случае косая черта представляет данные, а не завершает путь.  
  
 Передачи строки конструктору Uri приведет к следующим URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Разделение на сегменты пути приведет к появлению следующих элементов:  
  
 `Customer('1`  
  
 `3812')`  
  
 Это не является целью отправителя запроса.  
  
 Если **unescapeRequestUrl** атрибуту присваивается **false**, то при <xref:System.Net.HttpListener> получает запрос, он использует преобразованный URI вместо преобразованного из `http.sys` как входные данные <xref:System.Net.HttpListenerRequest.Url%2A> свойство.  
  
 Значение по умолчанию для **unescapeRequestUrl** атрибут **true**.  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Свойство может использоваться для получения текущего значения **unescapeRequestUrl** атрибут из применимые файлы конфигурации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить <xref:System.Net.HttpListener> класс при получении запроса для использования необработанных URI вместо преобразованного из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойство.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||
|-|-|  
|Пространство имен|System.Net|  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
