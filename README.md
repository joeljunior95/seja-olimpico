# seja-olimpico
Libraries: 
  * js-cookie: https://github.com/js-cookie/js-cookie ou 
    jquery-cookie: https://github.com/carhartl/jquery-cookie para criar cookies no client
    
  * paper.js: http://paperjs.org/about/ para fazer as animações
  
Dar uma olhada em CSS: Transition, Animation and Transforms

Talvez seja melhor usar SVG no lugar do paper.

<b>fazer isso funcionar e colocar todo o svg num arquivo separado para funcionar no safari (obs.: se mesmo assim não funcionar, tentar dar uma googada atrás de soluções para svg no safari):</b>
 var func = function (svg, circle) {
                if (!first) {
                    first = circle;
                    circle.setAttribute("fill", "#A51919");
                } else if (first !== circle) {
                    circle.setAttribute("fill", "#A51919");
                    var line = document.createElement("LINE");
//                    line.setAttribute("fill", "none");
                    line.setAttribute("stroke", "#A51919");
                    line.setAttribute("stroke-width", "3");
                    line.setAttribute("stroke-miterlimit", "10");
                    line.setAttribute("x1", first.getAttribute("cx"));
                    line.setAttribute("y1", first.getAttribute("cy"));
                    line.setAttribute("x2", circle.getAttribute("cx"));
                    line.setAttribute("y2", circle.getAttribute("cy"));
                    svg.appendChild(line);
                    console.log(svg.childNodes);
//                    var html = svg.innerHTML + "<line fill='none' stroke='#A51919' stroke-width='3' stroke-miterlimit='10' x1=" +
//                            first.getAttribute("cx") + " y1=" + first.getAttribute("cy") +
//                            " x2=" + circle.getAttribute("cx") + " y2=" + circle.getAttribute("cy") + " />";
//                    svg.innerHTML = html;
                    first = '';
//                    Cookies.set('teia', svg.innerHTML, {expires: 365});
//                    console.log(Cookies.get('teia'));
} else {
                    circle.setAttribute("fill", "#CCCCCC");
                    first = '';
                    var childs = svg.childNodes;
                    for (var child in childs) {
                        if (childs[child].nodeName === "LINE") {
                            console.log(childs[child]);
                        }
                    }

                }
            };
