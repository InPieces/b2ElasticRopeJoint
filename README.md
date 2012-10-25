b2ElasticRopeJoint
==================

Elastic Rope Joint with max length and "stretching".

Overwrite Box2D.h, b2Body,b2Joint.
Add b2ElasticRopeJoint.
Please Backup before testing ;)


Usage
=================

b2ElasticRopeJointDef jointDef;
        
jointDef.bodyA=b2BodyA;
jointDef.bodyB=b2BodyB;
jointDef.collideConnected = true;
jointDef.length = (b2BodyA->GetPosition() - b2BodyB->GetPosition()).Length();
//length is the max length the rope should get. After extending the length frequencyHz is used to stretch the rope and let it swing back 
jointDef.frequencyHz = 0.75;
//Used to define the stretching. Higher values = stiffer rope, lower values = more rubber like effect
        
world->CreateJoint(&jointDef)