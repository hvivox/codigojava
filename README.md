codigojava
==========
package com.br.hermes.controle;

import java.util.List;

import javax.faces.context.FacesContext;

import com.br.hermes.modelo.persistencia.entidades.ValueObject;

public class FacesUtil {

    public static String getRequestParameter(String name) {
        return (String) FacesContext.getCurrentInstance().getExternalContext()
            .getRequestParameterMap().get(name);
    }
    
    public static ValueObject getObjeto(List<? extends ValueObject> c, Long entityId) {
    	
    	ValueObject resultado = null;
    	
    	for (ValueObject vo : c) {
			if (vo.getEntityId().equals(entityId)) {
				return vo;
			}
		}
    	
    	return resultado;
    }

}
