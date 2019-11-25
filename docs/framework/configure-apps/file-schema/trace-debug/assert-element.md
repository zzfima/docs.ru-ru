---
title: Элемент <assert>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088945"
---
# <a name="assert-element"></a><span data-ttu-id="00fcb-102">Элемент > \<Assert</span><span class="sxs-lookup"><span data-stu-id="00fcb-102">\<assert> Element</span></span>
<span data-ttu-id="00fcb-103">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="00fcb-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

<span data-ttu-id="00fcb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00fcb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00fcb-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="00fcb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="00fcb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<assert >**</span><span class="sxs-lookup"><span data-stu-id="00fcb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>

## <a name="syntax"></a><span data-ttu-id="00fcb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00fcb-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00fcb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00fcb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00fcb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00fcb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00fcb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00fcb-110">Attributes</span></span>  
  
|<span data-ttu-id="00fcb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="00fcb-111">Attribute</span></span>|<span data-ttu-id="00fcb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="00fcb-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="00fcb-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="00fcb-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="00fcb-114">Указывает, следует ли отображать окно сообщения, если метод **Debug. Assert** возвращает **значение false**.</span><span class="sxs-lookup"><span data-stu-id="00fcb-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="00fcb-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="00fcb-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="00fcb-116">Указывает имя файла, в который будет записано сообщение, если **Debug. Assert** имеет значение **false**.</span><span class="sxs-lookup"><span data-stu-id="00fcb-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="00fcb-117">Атрибут ассертуиенаблед</span><span class="sxs-lookup"><span data-stu-id="00fcb-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="00fcb-118">значения</span><span class="sxs-lookup"><span data-stu-id="00fcb-118">Value</span></span>|<span data-ttu-id="00fcb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="00fcb-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="00fcb-120">Отображает окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="00fcb-120">Displays the message box.</span></span> <span data-ttu-id="00fcb-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00fcb-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="00fcb-122">Не отображает окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="00fcb-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00fcb-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00fcb-123">Child Elements</span></span>  
 <span data-ttu-id="00fcb-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="00fcb-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00fcb-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00fcb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="00fcb-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="00fcb-126">Element</span></span>|<span data-ttu-id="00fcb-127">Описание</span><span class="sxs-lookup"><span data-stu-id="00fcb-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00fcb-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00fcb-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="00fcb-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="00fcb-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00fcb-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="00fcb-130">Remarks</span></span>  
 <span data-ttu-id="00fcb-131">Оба атрибута в элементе **\<assert >** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="00fcb-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="00fcb-132">Можно отключить окна сообщений, не указывая файл для записи в него, или указать файл для записи сообщений при включении входящих в него окон сообщений.</span><span class="sxs-lookup"><span data-stu-id="00fcb-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00fcb-133">Пример</span><span class="sxs-lookup"><span data-stu-id="00fcb-133">Example</span></span>  
 <span data-ttu-id="00fcb-134">В следующем примере показано, как отключить отображение окон сообщений при вызове **Debug. Assert** и записи сообщений в `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="00fcb-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00fcb-135">См. также</span><span class="sxs-lookup"><span data-stu-id="00fcb-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="00fcb-136">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="00fcb-136">Trace and Debug Settings Schema</span></span>](index.md)
