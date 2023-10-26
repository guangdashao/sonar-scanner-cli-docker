docker build . -t harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-arm64 --platform linux/arm64 --network host --add-host deb.nodesource.com:104.22.5.26
docker push harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-arm64

docker build . -t harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-amd64 --platform linux/amd64 --add-host deb.nodesource.com:104.22.5.26
docker push harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-amd64

docker manifest create harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5 harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-amd64 harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-arm64
docker manifest push harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5 harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-amd64 harbor.ansteel.cn/lib/sonarsource/sonar-scanner-cli:5-arm64

github_token3 dckr_pat_BAPH946YU2t6XwiYe2D_XN4s3GY
