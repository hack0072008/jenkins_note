
# 备份
    备份jenkins的 JENKINS_HOME 即可，例如：
    cd /var/lib/ 
    tar -zcvf /var/lib/backup/jenkins_backup_`date +"%Y_%m_%d"`_backup.tar.gz --exclude=workspace --exclude=workspace@tmp ./jenkins/*
    
    注意：--exclude 选项为递归排除指定名称的目录，可多个

# 恢复
    解压备份好的文件到 JENKINS_HOME ,启动即可:
    java -Djava.awt.headless=true -DJENKINS_HOME=/opt/apps/jenkins/jenkins_home/jenkins -jar /opt/apps/jenkins/bin/2.104/jenkins.war --logfile=/var/log/jenkins/jenkins.log  --httpPort=9090 --debug=5


# 注意
    备份与恢复时的jenkins版本号必须相同

