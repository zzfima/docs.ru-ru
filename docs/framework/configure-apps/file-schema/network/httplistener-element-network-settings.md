---
title: '&lt;httpListener&gt; элемент (параметры сети)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a327f757f26c815d5b2cffe179af68bbe3d152eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744880"
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;httpListener&gt; элемент (параметры сети)
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
|unescapeRequestUrl|Логическое значение, указывающее, если <xref:System.Net.HttpListener> экземпляр использует необработанный неэкранированный URI вместо преобразованного URI.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 **UnescapeRequestUrl** атрибут указывает, если <xref:System.Net.HttpListener> использует необработанный неэкранированный URI вместо преобразованного URI, где все значения, закодированные преобразуются и выполняются другие действия нормализации.  
  
 Когда <xref:System.Net.HttpListener> экземпляр получает запрос через `http.sys` службы, он создает экземпляр в строке URI, предоставляемые `http.sys`и предоставляет его как <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> свойство.  
  
 `http.sys` Служба предоставляет две строки URI запроса:  
  
-   Необработанный URI  
  
-   Преобразованный URI  
  
 Необработанный URL-адрес является <xref:System.Uri?displayProperty=nameWithType> предоставленный в строке запроса HTTP-запроса:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Необработанный URI, предоставляемые `http.sys` для запроса, упомянутого выше, является «/ path /». Представляет строку, следующую за HTTP-командой, как она была отправлена по сети.  
  
 `http.sys` Служба создает преобразованный URI из информации, предоставленной в запросе, используя URI, предоставленный в строке запроса HTTP и заголовок узла для определения исходного сервера запроса должно быть перенаправлено в. Это делается путем сравнения сведений из запроса с набором зарегистрированных префиксов URI. В документации SDK сервера HTTP ссылается на этот преобразованный URI как HTTP_COOKED_URL структуры.  
  
 Чтобы иметь возможность сравнить запрос с зарегистрированными префиксами URI, необходимо сделать некоторые нормализацию в запросе. Для примера выше преобразованный URI будет следующим:  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` Службы объединяет <xref:System.Uri.Host%2A?displayProperty=nameWithType> значение свойства и строки в строку запроса для создания преобразованный URI. Кроме того `http.sys` и <xref:System.Uri?displayProperty=nameWithType> класса также выполняет следующее:  
  
-   Отмена переходов всех процентные значения.  
  
-   Преобразует закодированные символа ASCII в представление символов UTF-16. Обратите внимание, что символы UTF-8 и ANSI и DBCS поддерживаются также как знаки Юникода (кодировка Юникод с использованием формата % uXXXX).  
  
-   Выполняет другие действия нормализации, такие как сжатие пути.  
  
 Поскольку запрос не содержит никаких сведений о кодировке, используемой для закодированные значения, он может оказаться невозможно определить правильную кодировку только путем анализа закодированные значения.  
  
 Поэтому `http.sys` предоставляет два раздела реестра для изменения процесса:  
  
|Раздел реестра .|Значение по умолчанию|Описание|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Если значение равно нулю, `http.sys` принимает только URL-адреса в кодировке UTF-8.<br /><br /> Если ненулевое значение, `http.sys` также принимает кодировке ANSI или Двухбайтовой кодировке URL-адреса в запросах.|  
|FavorUTF8|1|Если ненулевое значение, `http.sys` всегда пытается расшифровать URL-адрес как UTF-8, если это преобразование завершается неудачей, и EnableNonUTF8 не равно нулю, Http.sys, а затем пытается расшифровать его как ANSI или DBCS.<br /><br /> Если значение равно нулю (и EnableNonUTF8 не равно нулю), `http.sys` пытается декодировать как ANSI или DBCS; Если этого не был выполнен успешно, он пытается преобразования UTF-8.|  
  
 Когда <xref:System.Net.HttpListener> получает запрос, он использует URI, преобразованные из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойства.  
  
 Нет необходимости поддерживать символы помимо символов и цифр в URI. Примером является следующий URI, который используется для извлечения сведений клиента для клиента номер «1/3812»:  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Обратите внимание, закодированные косую черту в универсальный код ресурса (% 2F). Это необходимо, поскольку в этом случае символ косой черты представляет данные, а не является разделителем пути.  
  
 Передача строки в конструктор Uri приведет к следующим URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Разделение на сегменты пути приведет к появлению следующих элементов:  
  
 `Customer('1`  
  
 `3812')`  
  
 Это не является целью отправителя запроса.  
  
 Если **unescapeRequestUrl** атрибута задано значение **false**, то при <xref:System.Net.HttpListener> получает запрос, он использует необработанный URI вместо преобразованного URI из `http.sys` как входные данные для <xref:System.Net.HttpListenerRequest.Url%2A> свойство.  
  
 Значение по умолчанию для **unescapeRequestUrl** атрибут **true**.  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Свойство может использоваться для получения текущего значения **unescapeRequestUrl** атрибут из применимые файлы конфигурации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить <xref:System.Net.HttpListener> класса при получении запроса для использования необработанных URI вместо преобразованного URI из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойства.  
  
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
