При разработке автотестов, часто сталкиваешься с однотипными элементами, у которых локаторы, по которым эти элементы могут быть идентифицированы, отличаются одним значением. Для улучшения читабельности кода и облегчения поддержки локаторов, удобно такие элементы группировать в перечисления. При этом отличающиеся части локаторов задавать в полях экземпляров.

Все такие перечисления на проекте, реализуют интерфейс ***MyLocatorInterface*** с одним единственным методом ****getLocator()****. Поэтому кроме удобства, повышения читабельности и облегчения поддержки таких перечислений, мы можем создать какие-то обобщенные методы, которые будут принимать в качестве аргумента экземпляры ***MyLocatorInterface***

В данном примере у перечисления ***DeviceType*** есть второе поле ****caption****. В реальном проекте тип устройства выбирается в комбобоксе (селекте) и после выбора в этом селекте отображается строка текста. Эта строка, является единственным, почем можно определить выбранное значения селекта (у селекта нет свойства value). Благодаря полю ***caption*** и методу ***typeOf*** можно легко выполнять проверки типа `DeviceType.typeOf(deviceTypeDropDown.getText())`

[DeviceType](src/main/java/DeviceType.java) - перечисление, реализующее интерфейс ***MyLocatorInterface***. Кроме этого имеет метод, который по строке возвращает тип перечисления

[DeviceModal](src/main/java/DeviceModal.java) -  PageObject модального окна выбора типа устройства. У DeviceModal есть комбобокс выбора типа устройства. 

[example](src/test/java/example.java) - пример. в котором показана смена типа устройства. 
