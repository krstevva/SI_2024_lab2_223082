# SI_2024_lab2_223082




public class SILab2 {
    public static boolean checkCart(List<Item> allItems, int payment){  //1
        if (allItems == null){ //1
            throw new RuntimeException("allItems list can't be null!"); //2
        }

        float sum = 0; //3

        for (int i = 0; i < allItems.size(); i++){ //4.1 4.2 4.3
            Item item = allItems.get(i);  //5
            if (item.getName() == null || item.getName().length() == 0){  //6
                item.setName("unknown");  //7
            }
            if (item.getBarcode() != null){  //8
                String allowed = "0123456789";   //9
                char chars[] = item.getBarcode().toCharArray();  
                for (int j = 0; j < item.getBarcode().length(); j++){  //10.1 10.2 10.3
                    char c = item.getBarcode().charAt(j);  //11
                    if (allowed.indexOf(c) == -1){  //12
                        throw new RuntimeException("Invalid character in item barcode!");  //13
                    }
                }
                if (item.getDiscount() > 0){ //14
                    sum += item.getPrice()*item.getDiscount();  //15
                } 
                else {
                    sum += item.getPrice();  //16
                }
            }   // 17
            else {
                throw new RuntimeException("No barcode!");  //18
            }
            if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0'){  //19
                sum -= 30;  //20
            }
        }   
        if (sum <= payment){  //21
            return true;  //22
        }
        else {
            return false;  //23
        }
    }  //24
}



Цикломатската вредност на овој код е 10 затоа што има 10 региони кои ги увидов со помош на Control Flow Graph, преку формулата V(G) = E–N+ 2. Бројот на ребра е 36, бројот на јазли е 28, па според формулата V(G) = 36-28+2=10 што ја дава вредноста за цикломатската комплексност. 


[Uploading Control Fl<mxfile host="Electron" modified="2024-05-26T10:47:47.337Z" agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/24.4.0 Chrome/120.0.6099.109 Electron/28.1.0 Safari/537.36" etag="00Qnc8qibUtrW9P-8rym" version="24.4.0" type="device">
  <diagram name="Page-1" id="DCu4wyWAYZ_ndygnWRrV">
    <mxGraphModel dx="1307" dy="1010" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="TUEeSB3WRywuPC623Gal-4" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" parent="1" source="TUEeSB3WRywuPC623Gal-1" target="TUEeSB3WRywuPC623Gal-3" edge="1">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-8" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" parent="1" source="TUEeSB3WRywuPC623Gal-1" target="TUEeSB3WRywuPC623Gal-7" edge="1">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-1" value="1" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" parent="1" vertex="1">
          <mxGeometry x="400" y="80" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-7" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="TUEeSB3WRywuPC623Gal-3" target="Ydah8nD8KQTIPVRDum0R-6">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-3" value="3" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" parent="1" vertex="1">
          <mxGeometry x="240" y="190" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-19" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" edge="1" parent="1" source="TUEeSB3WRywuPC623Gal-7" target="Ydah8nD8KQTIPVRDum0R-17">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="600" y="350" as="targetPoint" />
            <Array as="points">
              <mxPoint x="810" y="220" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-7" value="2" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" parent="1" vertex="1">
          <mxGeometry x="560" y="190" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-73" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" parent="1" edge="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="640" y="550" as="sourcePoint" />
            <mxPoint x="770" y="550" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-16" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" edge="1" parent="1" source="TUEeSB3WRywuPC623Gal-76" target="Ydah8nD8KQTIPVRDum0R-17">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="560" y="710" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="TUEeSB3WRywuPC623Gal-76" value="23" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" parent="1" vertex="1">
          <mxGeometry x="400" y="670" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-9" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-6" target="Ydah8nD8KQTIPVRDum0R-8">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-6" value="4.1" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="350" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-11" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-8" target="Ydah8nD8KQTIPVRDum0R-10">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-21" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-8" target="Ydah8nD8KQTIPVRDum0R-20">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-8" value="4.2" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="510" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-13" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-10" target="Ydah8nD8KQTIPVRDum0R-12">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-14" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-10" target="TUEeSB3WRywuPC623Gal-76">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-10" value="21" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="400" y="510" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-12" value="22" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="560" y="510" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-17" value="24" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="770" y="510" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-23" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-20" target="Ydah8nD8KQTIPVRDum0R-22">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-20" value="5" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="670" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-25" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-22" target="Ydah8nD8KQTIPVRDum0R-24">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-37" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-22" target="Ydah8nD8KQTIPVRDum0R-36">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-22" value="6" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="830" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-41" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-24" target="Ydah8nD8KQTIPVRDum0R-36">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="120" y="1050" as="targetPoint" />
            <Array as="points">
              <mxPoint x="121" y="1050" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-24" value="7" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="80" y="830" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-43" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-36" target="Ydah8nD8KQTIPVRDum0R-42">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-45" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-36" target="Ydah8nD8KQTIPVRDum0R-44">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-36" value="8" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="990" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-47" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-42" target="Ydah8nD8KQTIPVRDum0R-46">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-42" value="9" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="1150" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-92" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" edge="1" parent="1" target="Ydah8nD8KQTIPVRDum0R-17">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="481" y="1030" as="sourcePoint" />
            <mxPoint x="831" y="1030" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-44" value="18" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="400" y="990" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-49" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-46" target="Ydah8nD8KQTIPVRDum0R-93">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="440" y="1310" as="targetPoint" />
            <Array as="points">
              <mxPoint x="440" y="1270" />
              <mxPoint x="280" y="1270" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-46" value="10.1" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="400" y="1150" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-107" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0;entryY=1;entryDx=0;entryDy=0;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-56" target="Ydah8nD8KQTIPVRDum0R-93">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="180" y="1350" as="targetPoint" />
            <Array as="points">
              <mxPoint x="170" y="1830" />
              <mxPoint x="170" y="1378" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-56" value="10.3" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="1790" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-72" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-70" target="Ydah8nD8KQTIPVRDum0R-71">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-74" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-70" target="Ydah8nD8KQTIPVRDum0R-73">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-70" value="15" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="650" y="2060" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-77" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-71" target="Ydah8nD8KQTIPVRDum0R-75">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-71" value="14" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="490" y="2060" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-79" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-73" target="Ydah8nD8KQTIPVRDum0R-78">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-73" value="17" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="650" y="2220" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-114" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-75" target="Ydah8nD8KQTIPVRDum0R-73">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-75" value="16" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="490" y="2220" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-81" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-78" target="Ydah8nD8KQTIPVRDum0R-80">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-113" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=0.5;entryDx=0;entryDy=0;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-78" target="Ydah8nD8KQTIPVRDum0R-84">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="690" y="2610" as="targetPoint" />
            <Array as="points">
              <mxPoint x="690" y="2580" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-78" value="19" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="650" y="2380" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-85" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-80" target="Ydah8nD8KQTIPVRDum0R-84">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-80" value="20" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="490" y="2380" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-89" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;exitPerimeter=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-84" target="Ydah8nD8KQTIPVRDum0R-8">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="530" y="2640" as="sourcePoint" />
            <mxPoint x="230" y="555" as="targetPoint" />
            <Array as="points">
              <mxPoint x="530" y="2745" />
              <mxPoint x="9" y="2745" />
              <mxPoint x="9" y="550" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-84" value="4.3" style="ellipse;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="490" y="2540" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-96" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-93" target="Ydah8nD8KQTIPVRDum0R-95">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-111" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=-0.005;entryY=0.725;entryDx=0;entryDy=0;entryPerimeter=0;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-93" target="Ydah8nD8KQTIPVRDum0R-71">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="110" y="2080" as="targetPoint" />
            <Array as="points">
              <mxPoint x="90" y="1350" />
              <mxPoint x="90" y="2118" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-93" value="10.2" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="1310" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-100" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-95" target="Ydah8nD8KQTIPVRDum0R-99">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-95" value="11" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="1470" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-105" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-97">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="810" y="590" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-97" value="13" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="400" y="1470" width="80" height="80" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-101" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0.5;entryY=1;entryDx=0;entryDy=0;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-99" target="Ydah8nD8KQTIPVRDum0R-97">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="400" y="1670" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-103" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" edge="1" parent="1" source="Ydah8nD8KQTIPVRDum0R-99" target="Ydah8nD8KQTIPVRDum0R-56">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="Ydah8nD8KQTIPVRDum0R-99" value="12" style="ellipse;whiteSpace=wrap;html=1;aspect=fixed;" vertex="1" parent="1">
          <mxGeometry x="240" y="1620" width="80" height="80" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
ow Graph.drawio…]()

