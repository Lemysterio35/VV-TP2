# Extending PMD

Use XPath to define a new rule for PMD to prevent complex code. The rule should detect the use of three or more nested `if` statements in Java programs so it can detect patterns like the following:

```Java
if (...) {
    ...
    if (...) {
        ...
        if (...) {
            ....
        }
    }

}
```
Notice that the nested `if`s may not be direct children of the outer `if`s. They may be written, for example, inside a `for` loop or any other statement.
Write below the XML definition of your rule.

You can find more information on extending PMD in the following link: https://pmd.github.io/latest/pmd_userdocs_extending_writing_rules_intro.html

Use your rule with different projects and describe you findings below. See the [instructions](../sujet.md) for suggestions on the projects to use.

## Answer

<rule name="complexCode"
      language="java"
      message="More then 3 if detected"
      class="net.sourceforge.pmd.lang.rule.XPathRule" >
      <properties>
        <property name="maxStatements" type="Integer" value="10" min="1" max="40" description="Max number of statements per method"/>
        <property name="xpath">
    <![CDATA[
      //MethodDeclaration/Block[count(//ifStatement) > $maxStatements]
    ]]></property>
  </properties>
    <priority>3</priority>
</rule>
