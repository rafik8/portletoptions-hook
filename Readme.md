# Portlet options hook
This hook enable portal sign in users to maximize, minimize and restore portlets.

![Portlet options](/screenshots/portlet-options.png?raw=true "Portlet options")

## Configuration

In order to build the hook, add <liferay.home> to your maven profile (location of the Liferay server):
	
	<profiles> 
	...
	 <profile>
			<id>liferay62GA5</id>
            <properties>
				<liferay.home>/Labs/Liferay/servers/liferay-portal-6.2-ce-ga5</liferay.home>
            </properties>	
	 </profile>
	
	</profiles>

## Running the hook:

1) run the following maven command in order to deploy the hook:

mvn clean install liferay:deploy -Pliferay62GA5

2) check the hook deployment: login with a non admin account then check portlet options:

![Portlet options](/screenshots/portlet-options.png?raw=true "Portlet options")

## Integration
In you have already a hook project you can esaly integrate this hook in yours, you just need to copy **portlet__render-ext.jsp** under *custom_jsps/html/portal*.

In you have already hooked this file, copy these lines from **portlet_render-ext.jsp**:
    
    
    <%
    if (themedisplay.issignedin()) 
    { 
    	portletdisplay.setshowmaxicon(true);
    	portletdisplay.setshowminicon(true); 
    } 
    %>

## Reference

[Maximize and Minimize portlet option for signed in user](https://www.liferay.com/fr/web/jd.neha/blog/-/blogs/maximize-and-minimize-portlet-option-for-signed-in-user)

## License

[GNU Lesser General Public License (LGPL), Version 2.1](http://www.gnu.org/licenses/old-licenses/lgpl-2.1.txt)

