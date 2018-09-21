![picto](/doc/img/Logo_web-GeoCompiegnois.png)

# Documentation d'administration #

## Préambule

### Définition

Une surface est considérée comme consommée d'un point de vue des espaces naturels et agricoles lorsque celle-ci présente un état de retour irréversible à de tels usages. Dans le cadre du SCOT de l'ARC, cet état est considéré comme tel dans une opération d'aménagement lorsque le terrain est acquis, viabilisé et fouillé (d'un point de vue archéologique). Ce stade précéde le stade d'artificialisation et d'urbanisation au sens de la "construction", qui lui s'évalue plus généralement par la tâche urbaine.

### Méthodologie de détermination des surfaces SCOT

Le type de consommation des surfaces est déterminé de cette façon :

|Type|Description|
|:---|:---|
|Etalement|Consommation de surface par extension de l'urbanisation en zone AU|
|Densification|Consommation de surface de type "dent creuse" en zone U|
|Renouvellement urbain|Surface précédemment consommée et faisant l'objet d'une opération de renouvellement urbain, en zone U ou AU|



## Classes d'objet

L'ensemble des classes d'objets de gestion est stocké dans le schéma m_urbanisme_reg

Initialement, les classes d'objet ne concernaient que le territoire de l'ARC lors de l'approbation du SCOT fin 2012, soit 15 communes.
Avec l'évolution territoriale et l'élargissement à la commune de Lachelle et la CCBA de nouvelles classes se sont ajoutées pour ces territoires, afin de ne pas mélanger l'information avec les données initiales.
A des fins d'exploitation, les territoires concernés sont rassemblés dans une vue.

---

   `geo_scot_surf_conso_arc` : Surface considérée comme consommée au titre des espaces naturels et agricoles lors de l''approbation du SCOT fin 2012 de l''ARC (15 communes)

|Nom attribut | Définition | Type | Valeurs par défaut |
|:---|:---|:---|:---|
|id|Identifiant|bigint| |
|insee|Code INSEE|character(5)| |
|commune|Libellé de la commune|character varying(150)| |
|sup_ha|Superficie en ha|real| |
|src_geom|Référentiel de saisie|character varying(2)|'00'::bpchar|
|src_date|Année du millésime du référentiel de saisie|character varying(4)|'0000'::bpchar|
|date_sai|Horodatage de l'intégration en base de l'objet|timestamp without time zone|now()|
|date_maj|Horodatage de la mise à jour en base de l'objet|timestamp without time zone| |
|geom|Géométrie de l'objet|geometry(MultiPolygon,2154)| |

D'autres classes d'objet ont une structure identique à celle-ci, à savoir :

   `geo_scot_surf_conso_ccba` : Surface considérée comme rétrospectivement consommée fin 2012 au titre des espaces naturels et agricoles sur l''ex CCBA selon la méthodologie du SCOT de l'ARC
   
   `geo_scot_surf_conso_lach` : Surface considérée comme rétrospectivement consommée fin 2012 au titre des espaces naturels et agricoles sur la commune de Lachelle selon la méthodologie du SCOT de l'ARC

   `geo_v_scot_surf_conso_arcba` : Vue des surfaces considérées comme consommées fin 2012 au titre des espaces naturels et agricoles sur le territoire de l'ARCBA et selon la méthodologie du SCOT de l'ARC

---

   `geo_scot_hyp_surf_a_conso_arc` : Table géographique des hypothèses de localisation sommaire des surfaces à consommer approuvées au SCOT fin 2012 de l''ARC (15 communes).

|Nom attribut | Définition | Type | Valeurs par défaut |
|:---|:---|:---|:---|
|id|Identifiant|bigint| |
|ope_amgt|Nom de l'opération d'aménagement|character varying(80)| |
|destsurf|Destination d'usage de la surface à consommer|character varying(2)|'00'::bpchar|
|typeconso|Type de consommation de surface|character varying(2)|'00'::bpchar|
|insee|Code INSEE|character(5)| |
|commune|Libellé de la commune|character varying(150)| |
|sup_ha|Superficie en ha|real| |
|src_geom|Référentiel de saisie|character varying(2)|'00'::bpchar|
|src_date|Année du millésime du référentiel de saisie|character varying(4)|'0000'::bpchar|
|date_sai|Horodatage de l'intégration en base de l'objet|timestamp without time zone|now()|
|date_maj|Horodatage de la mise à jour en base de l'objet|timestamp without time zone| |
|geom|Géométrie de l'objet|geometry(MultiPolygon,2154)| |

---

   `geo_scot_hyp_surf_a_conso_ajust_arc` : Table géographique des ajustements des hypothèses de localisation sommaire des surfaces à consommer entre l'arrêt et l'approbation du SCOT de l''ARC (15 communes).

|Nom attribut | Définition | Type | Valeurs par défaut |
|:---|:---|:---|:---|
|id|Identifiant|bigint| |
|ope_amgt|Nom de l'opération d'aménagement|character varying(80)| |
|destsurf|Destination d'usage de la surface à consommer|character varying(2)|'00'::bpchar|
|typeconso|Type de consommation de surface|character varying(2)|'00'::bpchar|
|typeajust|Type d'ajustement des surfaces entre l'arrêt et l'approbation du SCOT de l''ARC|character varying(2)|'00'::bpchar|
|insee|Code INSEE|character(5)| |
|commune|Libellé de la commune|character varying(150)| |
|sup_ha|Superficie en ha|real| |
|src_geom|Référentiel de saisie|character varying(2)|'00'::bpchar|
|src_date|Année du millésime du référentiel de saisie|character varying(4)|'0000'::bpchar|
|date_sai|Horodatage de l'intégration en base de l'objet|timestamp without time zone|now()|
|date_maj|Horodatage de la mise à jour en base de l'objet|timestamp without time zone| |
|geom|Géométrie de l'objet|geometry(MultiPolygon,2154)| |


---

   `geo_scot_surf_suivi_conso_arcba` : Table géographique du suivi de la consommation des surfaces sur l'ARCBA.

|Nom attribut | Définition | Type | Valeurs par défaut |
|:---|:---|:---|:---|
|id|Identifiant|bigint| |
|ope_amgt|Nom de l'opération d'aménagement|character varying(80)| |
|destsurf|Destination d'usage de la surface à consommer|character varying(2)|'00'::bpchar|
|typeconso|Type de consommation de surface|character varying(2)|'00'::bpchar|
|annee_deb|Année de début de période de consommation de la surface|character varying(4)|'0000'::bpchar|
|annee_fin|Année de fin de période de consommation de la surface|character varying(4)|'0000'::bpchar|
|insee|Code INSEE|character(5)| |
|commune|Libellé de la commune|character varying(150)| |
|sup_ha|Superficie en ha|real| |
|src_geom|Référentiel de saisie|character varying(2)|'00'::bpchar|
|src_date|Année du millésime du référentiel de saisie|character varying(4)|'0000'::bpchar|
|date_sai|Horodatage de l'intégration en base de l'objet|timestamp without time zone|now()|
|date_maj|Horodatage de la mise à jour en base de l'objet|timestamp without time zone| |
|geom|Géométrie de l'objet|geometry(MultiPolygon,2154)| |

Cette classe d'objet est destinée à être modifiée contrairement aux précédentes, ceci afin d'effectuer le suivi de la consommation des surfaces du SCOT

---

## Liste de valeurs

`m_urbanisme_reg.lt_scot_destsurf` : Liste des valeurs permettant de décrire la destination de la surface

|Nom attribut | Définition | Type  | Valeurs par défaut |
|:---|:---|:---|:---|    
|code|Code|character varying(2)| |
|valeur|Valeur|character varying(80)| |

Valeurs possibles (héritées du standard PLU du CNIG et restreintes aux occurences adaptées pour la conso de surface au SCOT)

|Code|Valeur|
|:---|:---|
|00|Non renseigné|
|01|Habitat|
|02|Activité|
|03|Destination mixte habitat/activité|
|04|Loisirs et tourisme|
|05|Equipement|
|99|Autre|

---

`m_urbanisme_reg.lt_scot_typeconso` : Liste des valeurs permettant de décrire le type de consommation de la surface

|Nom attribut | Définition | Type  | Valeurs par défaut |
|:---|:---|:---|:---|    
|code|Code|character varying(2)| |
|valeur|Valeur|character varying(80)| |
|definition|Définition|character varying(254)| |

Valeurs possibles :

|Code|Valeur|Definition|
|:---|:---|:---|
|00|Non renseigné| |
|01|Etalement|Consommation de surface par extension de l'urbanisation en zone AU|
|02|Densification|Consommation de surface de type "dent creuse" en zone U|
|03|Renouvellement urbain|Surface précédemment consommée et faisant l'objet d'une opération de renouvellement urbain, en zone U ou AU|
|99|Autre| |

---

`m_urbanisme_reg.lt_scot_typeajust` : Liste des valeurs permettant de décrire le type d'ajustement opéré sur les hypothèses de surfaces à consommer pour le SCOT

|Nom attribut | Définition | Type  | Valeurs par défaut |
|:---|:---|:---|:---|    
|code|Code|character varying(2)| |
|valeur|Valeur|character varying(80)| |

Valeurs possibles :

|Code|Valeur|
|:---|:---|
|00|Non renseigné|
|01|Suppression|
|02|Ajout|
|99|Autre|

## Modèle conceptuel simplifié

![mcd](img/MCD.png)

## Schéma fonctionnel

![schema_fonctionnel](img/schema_fonctionnel_****.png)
