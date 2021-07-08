
# Useful TYPO3 PHPStorm LiveTemplates

Feel free to add some more TYPO3 Live Templates to this repository!

### How to setup

 1. Go to PHPStorm Settings -> Editor -> Live Templates
 2. Add a new one and choose PHP as interpreter (see [Docs](https://www.jetbrains.com/help/phpstorm/tutorial-creating-live-templates.html)) 

## 1. InjectMethod Generator

Generates injectMethods e.g. for controllers

![InjectMethodGenerator](images/injectmethod.gif)

**Example:**

```
/**  
 * @param \Vendor\Extension\Service\MyService $myService  
 */  
public function injectMyVar(\Vendor\Extension\Service\MyService $myService) {  
  $this->myService = $myService;  
}
```
**Live Template Code**

```
/**
 * @param $CLASSNAME$ $CLASSATTRIBUTE$$END$
 */
public function inject$CLASSATTRIBUTENAMEUPPER$($CLASSNAME$ $CLASSATTRIBUTE$) {
    $this->$CLASSATTRIBUTENAME$ = $CLASSATTRIBUTE$;
}
```
**Variable configuration**

|Name  | Expression |
|--|--|
| CLASSATTRIBUTE|  |
| CLASSNAME| clipboard() |
| CLASSATTRIBUTENAMEUPPER| capitalize(regularExpression(CLASSATTRIBUTE, "^.", "")) |
| CLASSATTRIBUTENAME| regularExpression(CLASSATTRIBUTE, "^.", "") |
