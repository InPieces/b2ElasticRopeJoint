b2ElasticRopeJoint v0.1
==================

Elastic Rope Joint with max length and "stretching".

Overwrite Box2D.h, b2Body,b2Joint.
Add b2ElasticRopeJoint.
Please Backup before testing ;)


Usage
=================

b2ElasticRopeJointDef jointDef;
        
jointDef.bodyA=b2BodyA;<br>
jointDef.bodyB=b2BodyB;<br>
jointDef.collideConnected = true;<br>
jointDef.length = (b2BodyA->GetPosition() - b2BodyB->GetPosition()).Length();<br>
//length is the max length the rope should get. After extending the length frequencyHz is used to stretch the rope and let it swing back<br>
jointDef.frequencyHz = 0.75;<br>
//Used to define the stretching. Higher values = stiffer rope, lower values = more rubber like effect
        
world->CreateJoint(&jointDef)