# Code of your exercise

Put here all the code created for this exercise

---


règle Xpath -> //IfStatement[ancestor::IfStatement[count(ancestor::IfStatement) >= 3]]



pmd check -f html -R /home/mehdy/Documents/VV/VV-ISTIC-TP2/exercises/ruleset.xml -d /home/mehdy/Documents/VV/VV-TP2-Codeàanalyser/commons-collections/src/ -r /home/mehdy/Documents/VV/VV-ISTIC-TP2/ReportPMDIf.html


<?xml version="1.0" encoding="UTF-8"?>
<ruleset xmlns="https://pmd.github.io/ruleset/2.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="https://pmd.github.io/ruleset/2.0.0 https://pmd.github.io/ruleset_2_0_0.xsd"
         name="DetectNestedIf"
         version="1.0">

    <description>
        Détecte les blocs `if` imbriqués à trois niveaux ou plus.
    </description>

    <rule name="Detect Nested If Statements"
          message="Évitez d'imbriquer des instructions if à plus de 3 niveaux de profondeur."
          class="net.sourceforge.pmd.lang.rule.xpath.XPathRule"
          language="java">
        <priority>2</priority>
        <properties>
            <property name="xpath">
                <value>
                    //IfStatement[ancestor::IfStatement[count(ancestor::IfStatement) >= 3]]
                </value>
            </property>
        </properties>
        <example>
            <![CDATA[
            if (a) {
                if (b) {
                    if (c) {
                        // Trop imbriqué
                    }
                }
            }
            ]]>
        </example>
    </rule>

</ruleset>

