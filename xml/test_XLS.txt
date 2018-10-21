<!DOCTYPE html>
<html>
<style>
<xsl:stylesheet version="1.0"
 xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
 <xsl:output omit-xml-declaration="yes" indent="yes"/>
 <xsl:strip-space elements="*"/>

 <xsl:template match="table">
   <table>
    <tr>
      <xsl:apply-templates select="col"/>
    </tr>
    <xsl:apply-templates select="output"/>
   </table>
 </xsl:template>

 <xsl:template match="col">
  <td width="{@size}"><xsl:value-of select="."/></td>
 </xsl:template>

 <xsl:template match="output">
  <tr>
   <xsl:apply-templates/>
  </tr>
 </xsl:template>

 <xsl:template match="row">
  <td><xsl:value-of select="."/></td>
 </xsl:template>
</xsl:stylesheet>

</body>
</html>
